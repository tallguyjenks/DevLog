---
id: JlaEgG3XIzcsET3Bkxza5
title: Group By
desc: ''
updated: 1641413160371
created: 1641105063934
stub: false
isDir: false
---

```sql
SELECT Age, Name, COUNT(Name)
FROM Person 
GROUP BY Age
HAVING Age > 50
```

The `GROUP BY` statement consolidates the records based on the aggregate function used. The aggregate function could be something like `COUNT()` or `SUM()` etc. and it says group by `Age`.

So it will find each distinct `Age` and then group together a `COUNT()` or `SUM()` of all the records for each of those unique `Age`'s.

The filtering occurs post-aggregation when `HAVING` is applied to not return the aggregates for any `Age`'s that are _> 50_



