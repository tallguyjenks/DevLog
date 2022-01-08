---
tags: 💻️/TSQL 
publish: true
aliases:
  - 
cssclass: 
created: 2022-01-07 1714
updated: 2022-01-07 1714
---

# [[T-SQL LIKE Predicate]]

---

Used with [[T-SQL Wild Cards|Wild Cards]], the `LIKE` predicate looks at a [[T-SQL Wild Cards|Wild Card]] string and runs the [[Regular Expressions|Regular Expression]] pattern matching operation.

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

---

- Tags: 
	- 
- Reference:
	- 
- Related:
	- 
