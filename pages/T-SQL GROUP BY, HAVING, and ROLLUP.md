---
tags:
#  - 🌱️
#  - 🌞️
#  - 🌲️
aliases: 
  - GROUP BY
  - HAVING
  - ROLLUP
cssclass: 
---

#### [[T-SQL GROUP BY, HAVING, and ROLLUP]]

---

```sql
SELECT Age, Name, COUNT(Name)
FROM Person 
GROUP BY Age
HAVING Age > 50
```

The `GROUP BY` statement consolidates the records based on the aggregate function used. The aggregate function could be something like `COUNT()` or `SUM()` etc. and it says group by `Age`.

So it will find each distinct `Age` and then group together a `COUNT()` or `SUM()` of all the records for each of those unique `Age`'s.

The filtering occurs post-aggregation when `HAVING` is applied to not return the aggregates for any `Age`'s that are *> 50*

### The 'HAVING' Clause

The having clause is like the `WHERE` clause except you can use aggregate functions like `COUNT()` and `SUM()` with it.

```sql
SELECT Age, Name, COUNT(Name)
FROM Person 
GROUP BY Age
HAVING COUNT(Name) > 50
```

### The 'RollUp' Sub-Clause

```sql
SELECT Age, Name, COUNT(Name)
FROM Person 
GROUP BY Age WITH ROLLUP
HAVING Age > 50
```

Adds an additional record item of the results of the initial aggregation option.

So: if you had a grouping of `COUNT()`'s for each `Age` already totaled up, the `ROLLUP` looks at all of those totals and aggregates them into a grand total.

---
Tags: 

Reference:

Related:
