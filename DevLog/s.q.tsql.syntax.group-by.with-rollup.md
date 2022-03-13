---
id: 3dr9g8iq4e1kbrcoihpml89
title: With Rollup
desc: ''
updated: 1641413167348
created: 1641413167348
---


### The 'RollUp' Sub-Clause

```sql
SELECT Age, Name, COUNT(Name)
FROM Person 
GROUP BY Age WITH ROLLUP
HAVING Age > 50
```

Adds an additional record item of the results of the initial aggregation option.

So: if you had a grouping of `COUNT()`'s for each `Age` already totaled up, the `ROLLUP` looks at all of those totals and aggregates them into a grand total.
