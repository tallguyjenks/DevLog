---
id: 6uvtwuf3kptuwuesn0jznwe
title: Having
desc: ''
updated: 1641413206135
created: 1641413206135
---


### The 'HAVING' Clause

The having clause is like the `WHERE` clause except you can use aggregate functions like `COUNT()` and `SUM()` with it.

```sql
SELECT Age, Name, COUNT(Name)
FROM Person 
GROUP BY Age
HAVING COUNT(Name) > 50
```
