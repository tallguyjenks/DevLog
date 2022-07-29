
> If you have to compare string values on a regular basis, and especially if you have to compare more than one column at a time, instead of comparing the columns directly, hash the columns first. Hashing creates a string based on the encryption algorithm you select. You can pass in concatenated string values. The ultimate benefit is that all the algorithms generate a value that is a set number of characters. This comes in handy for storing this value when it comes time for loading junk dimensions into data warehouses.
> You cannot use `HASHBYTES()` on `NVARCHAR(MAX)` in SQL Server. `HASHBYTES` has a 4,000-character limit for `NVARCHAR`. Technically, you can get around this programmatically, but if your data is longer than 4,000 characters, I’d suggest looking for another way to identify the record.
>
> -- <https://tutorials.massstreet.net/v/transact-sql/solutions-to-real-world-problems/lesson-63.-using-hashbytes-to-compare-character-strings>


```sql
DECLARE @Statement1 NVARCHAR(255)
DECLARE @Statement2 NVARCHAR(255)

SET @Statement1 = 'Army And Navy Play For Second'
SET @Statement2 = 'Rock Chalk Jayhawk'

PRINT LEN(@Statement1)
PRINT LEN(@Statement2)

PRINT HASHBYTES('MD5', @Statement1)
PRINT HASHBYTES('MD5', @Statement2)

PRINT LEN(HASHBYTES('MD5', @Statement1))
PRINT LEN(HASHBYTES('MD5', @Statement2))

-- 29
-- 18
-- 0x9A6A731EB1D5FE8F3B93A576A9740E3E
-- 0xFDEFE8D5B2FF212060E733A0A01A1A7F
-- 16
-- 16
```

```sql
DECLARE @Statement1 NVARCHAR(255)
DECLARE @Statement2 NVARCHAR(255)

SET @Statement1 = 'WalMart'
SET @Statement2 = 'walmart'


PRINT HASHBYTES('MD5', @Statement1) --0xDE2E98EE55B1B249B711300DE7047C75
PRINT HASHBYTES('MD5', @Statement2) --0xC48604C9A656E09D87E99B820499D430
```

## Using Pipe To Hash Multiple Columns For Matching

<https://tutorials.massstreet.net/v/transact-sql/solutions-to-real-world-problems/lesson-64.-using-pipe-to-hash-multiple-columns-for-matching>

> When using the `HASHBYTES()` function in SQL Server to hash multiple columns for matching, use `CONCAT()` and separate values with a pipe.
> Usually, the values in columns are disparate enough that you really do not have to worry. For example, it was years before I actually discovered an edge case. However, I did discover at least one scenario where concatenating the columns was not enough to develop a unique record. This occurred in a table with few columns and small amounts of data.
> A better approach is to just `CONCAT()` columns with a pipe between values. Since this character is rarely used, it lowers the probability of having different values hash the same.

```sql
DECLARE @SampleStageTable AS TABLE(ID INT, VALUE1 NVARCHAR(10), VALUE2 NVARCHAR(10))

INSERT INTO @SampleStageTable(ID, VALUE1, VALUE2)
SELECT 1, '012','345'
UNION
SELECT 2, '01','2345'

SELECT * FROM @SampleStageTable
-------------------------------------------------------------------------------------
DECLARE @SampleStageTable AS TABLE(ID INT, VALUE1 NVARCHAR(10), VALUE2 NVARCHAR(10))

INSERT INTO @SampleStageTable(ID, VALUE1, VALUE2)
SELECT 1, '012','345'
UNION
SELECT 2, '01','2345'


SELECT ID, VALUE1, VALUE2, HASHBYTES('MD5', CONCAT(VALUE1, VALUE2)) AS ROWHASH
FROM @SampleStageTable
```

So separate columns with a `|`

```sql
DECLARE @SampleStageTable AS TABLE(ID INT, VALUE1 NVARCHAR(10), VALUE2 NVARCHAR(10))

INSERT INTO @SampleStageTable(ID, VALUE1, VALUE2)
SELECT 1, '012','345'
UNION
SELECT 2, '01','2345'


SELECT ID, VALUE1, VALUE2, HASHBYTES('MD5', CONCAT(VALUE1,'|', VALUE2)) AS ROWHASH
FROM @SampleStageTable
```
