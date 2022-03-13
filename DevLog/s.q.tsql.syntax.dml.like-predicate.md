---
id: qt6tj6odl7qbodpavaed9bc
title: Like Predicate
desc: ''
updated: 1641413724286
created: 1641105063936
stub: false
isDir: false
---


Used with [[T-SQL Wild Cards|s.q.tsql.syntax.wild-cards]], the `LIKE` predicate looks at a [[s.q.tsql.syntax.wild-cards]] string and runs the [[s.o.regular-expressions]] pattern matching operation.

```sql
SELECT Name
FROM Person
WHERE Name LIKE 'Jo*' -- wild card matching on strings
/*
	Result would be any of these:
	John
	Jon
	Johnny
	Jonny
	Etc.
*/

```
