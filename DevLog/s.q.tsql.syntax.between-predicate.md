---
id: fgdibswbaepsiao0wqje69e
title: Between Predicate
desc: ''
updated: 1641412769490
created: 1641105063931
stub: false
isDir: false
---


The `BETWEEN` predicate is used to signify an **inclusive** range of values for a condition. You use `BETWEEN` in conjunction with the `AND` operator to mark the 2 ranges your result values should fall between.

```sql
SELECT Age
FROM Person
WHERE Age BETWEEN 55 AND 65 -- This includes both the ages 55 and 65 as it is inclusive
```
