

## Link

<https://www.mssqltips.com/sqlservertip/5118/sql-server-cte-vs-temp-table-vs-table-variable-performance-test/>

## Related

It appears that [[CTE's|s.q.tsql.dbos.common-table-expressions]] are the most efficient and fastest of the temporary result set options and even [[s.q.tsql.dbos.temp-tables]] are better than [[s.q.tsql.syntax.table-variables]]

## Notes

```sql
-- CTE
WITH t (customerid, lastorderdate) AS 
 (SELECT customerid, max(orderdate) 
  FROM sales.SalesOrderHeader
  GROUP BY customerid)
SELECT * 
FROM sales.salesorderheader soh
INNER JOIN t ON soh.customerid=t.customerid AND soh.orderdate=t.lastorderdate
GO

-- Temporary table
CREATE TABLE #temptable (customerid [int] NOT NULL PRIMARY KEY, lastorderdate [datetime] NULL);

INSERT INTO #temptable
SELECT customerid, max(orderdate) as lastorderdate 
FROM sales.SalesOrderHeader
GROUP BY customerid;

SELECT * 
FROM sales.salesorderheader soh
INNER JOIN #temptable t ON soh.customerid=t.customerid AND soh.orderdate=t.lastorderdate

DROP TABLE #temptable
GO

-- Table variable
DECLARE @tablevariable TABLE (customerid [int] NOT NULL PRIMARY KEY, lastorderdate [datetime] NULL);

INSERT INTO @tablevariable
SELECT customerid, max(orderdate) as lastorderdate 
FROM sales.SalesOrderHeader
GROUP BY customerid;

SELECT * 
FROM sales.salesorderheader soh
INNER JOIN @tablevariable t ON soh.customerid=t.customerid AND soh.orderdate=t.lastorderdate
GO
```

---

![sql profiler](/assets/images/2022-03-03-12-49-56.png)

---

Here are the updated queries which add a WHERE clause to each statement we tested above.

```sql
-- CTE
WITH t (customerid, lastorderdate) AS 
 (SELECT customerid, max(orderdate) 
  FROM sales.SalesOrderHeader
  WHERE customerid=27604 
  GROUP BY customerid)
SELECT * 
FROM sales.salesorderheader soh
INNER JOIN t ON soh.customerid=t.customerid AND soh.orderdate=t.lastorderdate
GO

--Temp table
CREATE TABLE #temptable (customerid [int] NOT NULL PRIMARY KEY, lastorderdate [datetime] NULL);

INSERT INTO #temptable
SELECT customerid, max(orderdate) as lastorderdate 
FROM sales.SalesOrderHeader
WHERE customerid=27604
GROUP BY customerid;

SELECT * 
FROM sales.salesorderheader soh
INNER JOIN #temptable t ON soh.customerid=t.customerid AND soh.orderdate=t.lastorderdate

DROP TABLE #temptable
GO

--Table variable
DECLARE @tablevariable TABLE (customerid [int] NOT NULL PRIMARY KEY, lastorderdate [datetime] NULL);

INSERT INTO @tablevariable
SELECT customerid, max(orderdate) as lastorderdate 
FROM sales.SalesOrderHeader
WHERE customerid=27604
GROUP BY customerid;

SELECT * 
FROM sales.salesorderheader soh
INNER JOIN @tablevariable t ON soh.customerid=t.customerid AND soh.orderdate=t.lastorderdate
GO
```

---

![sql profiler 2](/assets/images/2022-03-03-12-50-45.png)
