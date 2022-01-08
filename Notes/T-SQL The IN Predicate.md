---
tags: 💻️/TSQL 
publish: true
aliases:
  - 
cssclass: 
created: 2022-01-07 1719
updated: 2022-01-07 1719
---

# [[T-SQL The IN Predicate]]

---

Similar to [[T-SQL BETWEEN Predicate|BETWEEN]], the `IN` predicate denotes not a range between value A and B but any value in a list that doesnt lend itself to ranging like specific text values or disjointed numerical values:

```sql
SELECT Age
FROM Person
WHERE Age IN (55, 65, 80) -- This matches only to those 3 listed numbers

-- OR

SELECT Name
FROM Person
WHERE Name IN ('Bob', 'Joe', 'Mary', 'Sue') -- matching on strings
```

---

- Tags: 
	- 
- Reference:
	- 
- Related:
	- 
