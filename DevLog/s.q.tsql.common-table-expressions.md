---
id: d8njr2chsv4x5mj3k8746la
title: Common Table Expressions
desc: ''
updated: 1641412863950
created: 1641105063932
stub: false
isDir: false
---


A `CTE` is a temporary result set that you can reference within another `SELECT`, [[s.q.tsql.dml.insert-into]], [[T-SQL UPDATE|s.q.tsql.dml.update]], or [[T-SQL DELETE|s.q.tsql.dml.delete]] statement.

A `CTE` always returns a result set. They are used to simplify queries, like eliminating a derived table from the main query body:

```sql
WITH My_Table (Age, Counts)
AS
(
	SELECT Age, COUNT(Name) AS Counts
	FROM Source_Table
	WHERE Age > 55
	GROUP BY Age
)
SELET *
FROM My_Table
ORDER BY Age
GO
```

No [[s.q.tsql.temp-tables]] assignment, no need to make an intermediary table. I like to this of `CTE`'s like Rice paddy fields where the data like the water just flows downward into the next query or `CTE`.

