
> If you are calling a proc from an SSIS package, there is no need to get the row count of the records impacted by your query. By setting NOCOUNT to ON, you can significantly boost performance due to the drop in network traffic.
>
> -- <https://tutorials.massstreet.net/v/transact-sql/solutions-to-real-world-problems/lesson-49.-boost-performance-when-calling-a-stored-proc-from-ssis>

```sql
USE AdventureWorks2016

DROP PROCEDURE IF EXISTS dbo.usp_NoCountExample
GO

CREATE PROCEDURE dbo.usp_NoCountExample

AS
BEGIN

SET NOCOUNT ON;

SELECT *
FROM Sales.SalesOrderHeader soh
JOIN Sales.SalesOrderDetail sod
ON soh.SalesOrderID = sod.SalesOrderID

SET NOCOUNT OFF;

END
GO
```
