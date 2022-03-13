---
id: hl8lyqzvwxuwsrlqxlvsnl2
title: Nolock
desc: ''
updated: 1646690532149
created: 1646356043811
---

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
