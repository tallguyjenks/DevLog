
![[r.(.2022.03.03.understanding-the-sql-server-nolock-hint]]

Better way to get dirty reads on tables

```sql
USE AdventureWorks2016

SET TRANSACTION ISOLATION LEVEL READ UNCOMMITTED


SELECT *
FROM [Sales].[SalesOrderHeader] soh
JOIN [Sales].[SalesOrderDetail] sod
ON soh.SalesOrderID = sod.SalesOrderID

SET TRANSACTION ISOLATION LEVEL READ COMMITTED
```
