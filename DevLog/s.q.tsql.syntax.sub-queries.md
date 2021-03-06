---
id: x91g14s1nh6ab61137ea7y5
title: Sub Queries
desc: ''
updated: 1641414029592
created: 1641105063938
stub: false
isDir: false
---


A sub-query is a nested `SELECT` statement inside of another parent `SELECT` statement.

A usage of this is to select a record set from which you then want to manipulate and operate on after that initial pool is generated:

```sql
SELECT P.Age
FROM (
	SELECT P1.*
	FROM PERSON P1
	WHERE P1.Name = 'Paul'
)
```

In this example the first operation performed is the gathering of all records from the `P1` table where the `Name` field contains the string value _Paul_. Then from that result set we are selecting the `Age` field from that initial result set.

With sub-queries:

A Required `SELECT` statement list
A Required `FROM` clause
An Optional `WHERE` clause
An Optional `GROUP BY` clause
An Optional `HAVING` clause
But **NO** `ORDER BY` clause this will throw an _error_

Sub queries can be used anywhere an expression is allowed. This includes the `SELECT` portion of a query, the `FROM` clause, the `WHERE` clause, `JOIN`'s, `GROUP BY`'s.
