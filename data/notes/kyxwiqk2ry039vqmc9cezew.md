

## Date Dimension Table

```sql
/**************************************************************************************************************************\
|===========================================================================================================================|
|                                                                                                                           |
|                                                                                                                           |
| Reference Article: https://www.mssqltips.com/sqlservertip/4054/creating-a-date-dimension-or-calendar-table-in-sql-server/ |
|                                                                                                                           |
|                                                                                                                           |
|===========================================================================================================================|
***************************************************************************************************************************/

-- FIXME Change all instances of `Ticketer` to the database chosen to house these DBO's
USE Ticketer

IF OBJECT_ID('Ticketer.dbo.HolidayDimension') IS NOT NULL DROP TABLE HolidayDimension
IF OBJECT_ID('Ticketer.dbo.DateDimension') IS NOT NULL DROP TABLE DateDimension
IF OBJECT_ID('Ticketer.dbo.TheCalendar') IS NOT NULL DROP VIEW TheCalendar

-- prevent set or regional settings from interfering with
-- interpretation of dates / literals
SET DATEFIRST  7 -- 1 = Monday, 7 = Sunday
    , DATEFORMAT mdy
    , LANGUAGE   US_ENGLISH;

-- Start and End points
DECLARE @StartDate  DATE = '20100101';
DECLARE @CutoffDate DATE = DATEADD(DAY, -1, DATEADD(YEAR, 30, @StartDate));

-- First CTE generating the list of numbers from the Start and End points
;WITH seq(n) AS
(
	SELECT 0 UNION ALL SELECT n + 1 FROM seq
	WHERE n < DATEDIFF(DAY, @StartDate, @CutoffDate)
),
d(d) AS
( -- Second CTE generating an ISO 8601 Date from the numbers
	SELECT DATEADD(DAY, n, @StartDate) FROM seq
),
src AS
( -- Third CTE taking the generated dates and parsing them into the pertinent information
	SELECT
		  TheDate         = CONVERT(DATE,		d)
		, TheDay          = DATEPART(DAY,       d)
		, TheDayName      = DATENAME(WEEKDAY,   d)
		, TheWeek         = DATEPART(WEEK,      d)
		, TheISOWeek      = DATEPART(ISO_WEEK,  d)
		, TheDayOfWeek    = DATEPART(WEEKDAY,   d)
		, TheMonth        = DATEPART(MONTH,     d)
		, TheMonthName    = DATENAME(MONTH,     d)
		, TheQuarter      = DATEPART(Quarter,   d)
		, TheYear         = DATEPART(YEAR,      d)
		, TheFirstOfMonth = DATEFROMPARTS(YEAR(d), MONTH(d), 1)
		, TheLastOfYear   = DATEFROMPARTS(YEAR(d), 12, 31)
		, TheDayOfYear    = DATEPART(DAYOFYEAR, d)
	FROM d
),
dim AS
( -- Fourth CTE adding additional information of value
	SELECT
		  TheDate
		, TheDay
		, TheDaySuffix       = CONVERT(CHAR(2), CASE
												WHEN TheDay / 10 = 1 THEN 'th'
												ELSE 
													CASE RIGHT(TheDay, 1)
														WHEN '1' THEN 'st'
														WHEN '2' THEN 'nd'
														WHEN '3' THEN 'rd'
														ELSE 'th' END
												END)
		, TheDayName
		, TheDayOfWeek
		, TheDayOfWeekInMonth = CONVERT(TINYINT, ROW_NUMBER() OVER (PARTITION BY TheFirstOfMonth, TheDayOfWeek ORDER BY TheDate))
		, TheDayOfYear
		, IsWeekend           = CASE WHEN TheDayOfWeek IN (
									CASE @@DATEFIRST
									WHEN 1 THEN 6
									WHEN 7 THEN 1
									END, 7
								) 
								THEN 1 ELSE 0 END
		, TheWeek
		, TheISOweek
		, TheFirstOfWeek      = DATEADD(DAY, 1 - TheDayOfWeek, TheDate)
		, TheLastOfWeek       = DATEADD(DAY, 6, DATEADD(DAY, 1 - TheDayOfWeek, TheDate))
		, TheWeekOfMonth      = CONVERT(TINYINT, DENSE_RANK() OVER (PARTITION BY TheYear, TheMonth ORDER BY TheWeek))
		, TheMonth
		, TheMonthName
		, TheFirstOfMonth
		, TheLastOfMonth      = MAX(TheDate) OVER (PARTITION BY TheYear, TheMonth)
		, TheFirstOfNextMonth = DATEADD(MONTH, 1, TheFirstOfMonth)
		, TheLastOfNextMonth  = DATEADD(DAY, -1, DATEADD(MONTH, 2, TheFirstOfMonth))
		, TheQuarter
		, TheFirstOfQuarter   = MIN(TheDate) OVER (PARTITION BY TheYear, TheQuarter)
		, TheLastOfQuarter    = MAX(TheDate) OVER (PARTITION BY TheYear, TheQuarter)
		, TheYear
		, TheISOYear          = TheYear - CASE WHEN TheMonth = 1 AND TheISOWeek > 51 THEN 1
											   WHEN TheMonth = 12 AND TheISOWeek = 1  THEN -1
											   ELSE 0 END
		, TheFirstOfYear      = DATEFROMPARTS(TheYear, 1,  1)
		, TheLastOfYear
		, IsLeapYear          = CONVERT(BIT, CASE WHEN TheYear % 400 = 0 OR (TheYear % 4 = 0 AND TheYear % 100 <> 0) THEN 1 ELSE 0 END)
		, Has53Weeks          = CASE WHEN DATEPART(WEEK, TheLastOfYear) = 53 THEN 1 ELSE 0 END
		, Has53ISOWeeks       = CASE WHEN DATEPART(ISO_WEEK, TheLastOfYear) = 53 THEN 1 ELSE 0 END
		, YYYYMM			  = CONCAT(TheYear, CASE WHEN LEN(TheMonth) = 1 THEN CONCAT('0', TheMonth) ELSE TheMonth END) 
		, MMYYYY              = CONVERT(CHAR(2), CONVERT(CHAR(8), TheDate, 101)) + CONVERT(CHAR(4), TheYear)
		, Style101            = CONVERT(CHAR(10), TheDate, 101)
		, Style103            = CONVERT(CHAR(10), TheDate, 103)
		, Style112            = CONVERT(CHAR(8),  TheDate, 112)
		, Style120            = CONVERT(CHAR(10), TheDate, 120)
	FROM src
)
-- CREATE THE DATE DIMENSION TABLE
SELECT *
INTO dbo.DateDimension
FROM dim
ORDER BY TheDate
OPTION (MAXRECURSION 0);

CREATE UNIQUE CLUSTERED INDEX CIX_DateDimension ON dbo.DateDimension(TheDate);

-- CREATE THE HOLIDAY DIMENSION TABLE
CREATE TABLE dbo.HolidayDimension
(
	TheDate DATE NOT NULL,
	HolidayText NVARCHAR(255) NOT NULL,
	CONSTRAINT FK_DateDimension FOREIGN KEY(TheDate) REFERENCES dbo.DateDimension(TheDate)
);

CREATE CLUSTERED INDEX CIX_HolidayDimension ON dbo.HolidayDimension(TheDate);

;WITH x AS
(
	SELECT
		  TheDate
		, TheFirstOfYear
		, TheDayOfWeekInMonth
		, TheMonth
		, TheDayName
		, TheDay
		, TheLastDayOfWeekInMonth = ROW_NUMBER() OVER
		  (
			PARTITION BY TheFirstOfMonth, TheDayOfWeek
			ORDER BY TheDate DESC
		  )
	FROM dbo.DateDimension
),
s AS
(
	SELECT
		  TheDate
		, HolidayText = CASE
		WHEN (TheDate = TheFirstOfYear)
			THEN 'New Year''s Day'
		WHEN (TheDayOfWeekInMonth = 3 AND TheMonth = 1 AND TheDayName = 'Monday')
			THEN 'Martin Luther King Day'		-- (3rd Monday in January)
		WHEN (TheDayOfWeekInMonth = 3 AND TheMonth = 2 AND TheDayName = 'Monday')
			THEN 'President''s Day'				-- (3rd Monday in February)
		WHEN (TheMonth = 3 AND TheDay = 31)
			THEN 'Cesar Chavez Day'
		WHEN (TheLastDayOfWeekInMonth = 1 AND TheMonth = 5 AND TheDayName = 'Monday')
			THEN 'Memorial Day'					-- (last Monday in May)
		WHEN (TheMonth = 7 AND TheDay = 4)
			THEN 'Independence Day'				-- (July 4th)
		WHEN (TheDayOfWeekInMonth = 1 AND TheMonth = 9 AND TheDayName = 'Monday')
			THEN 'Labour Day'					-- (first Monday in September)
		WHEN (TheMonth = 11 AND TheDay = 11)
			THEN 'Veterans'' Day'				-- (November 11th)
		WHEN (TheDayOfWeekInMonth = 4 AND TheMonth = 11 AND TheDayName = 'Thursday')
			THEN 'Thanksgiving Day'             -- (Thanksgiving Day ()fourth Thursday in November)
		WHEN (TheMonth = 12 AND TheDay = 25)
			THEN 'Christmas Day'
		END
	FROM x
	WHERE (TheDate = TheFirstOfYear)													-- New Years
		OR (TheDayOfWeekInMonth = 3     AND TheMonth = 1  AND TheDayName = 'Monday')	-- MLK Day
		OR (TheDayOfWeekInMonth = 3     AND TheMonth = 2  AND TheDayName = 'Monday')	-- Presidents Day
		OR (TheMonth = 3				AND TheDay = 31)								-- Cesar Chavez Day
		OR (TheLastDayOfWeekInMonth = 1 AND TheMonth = 5  AND TheDayName = 'Monday')	-- Memorial Day
		OR (TheMonth = 7				AND TheDay = 4)									-- Independence Day
		OR (TheDayOfWeekInMonth = 1     AND TheMonth = 9  AND TheDayName = 'Monday')	-- Labor Day
		OR (TheMonth = 11				AND TheDay = 11)								-- Veterans Day
		OR (TheDayOfWeekInMonth = 4     AND TheMonth = 11 AND TheDayName = 'Thursday')	-- Thanksgiving Day
		OR (TheMonth = 12				AND TheDay = 25)								-- Christmas Day
)
INSERT dbo.HolidayDimension(TheDate, HolidayText)

SELECT TheDate, HolidayText FROM s
UNION ALL
SELECT DATEADD(DAY, 1, TheDate), 'Black Friday' -- Special Case
FROM s WHERE HolidayText = 'Thanksgiving Day'
ORDER BY TheDate;
GO

CREATE VIEW dbo.TheCalendar
AS
	SELECT
		  d.*
		, IsHoliday = CASE WHEN h.TheDate IS NOT NULL THEN 1 ELSE 0 END
		, h.HolidayText
	FROM dbo.DateDimension AS d
		LEFT OUTER JOIN dbo.HolidayDimension AS h
			ON d.TheDate = h.TheDate;
```
