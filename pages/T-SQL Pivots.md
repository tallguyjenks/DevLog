---
tags:
#  - 🌱️
#  - 🌞️
#  - 🌲️
aliases: 
  - Pivots
  - Pivot
cssclass: 
---

#### [[T-SQL Pivots]]

---

### Pivoting

the Pivot is like a transcribe operator in excel. You take the top left point, anchor it and then flips the axis' and their values.

```sql
SELECT Name
	,pvt.Low
	,pvt.Med
	,pvt.High
	,pvt.Ultra
FROM Person
PIVOT
	(SUM(Total) FOR Level IN ([Low], [Med], [High], [Ultra])
	) AS pvt
```

| Before       | After |
| ------------ | ----- |
| ![[#^ccac61]] | ![[#^5c0e2c]] |

### UN-pivoting

```sql
SELECT Name
	,upvt.Level
	,upvt.Total
FROM Person
UNPIVOT
	(Total FOR Level IN ([Low], [Med], [High], [Ultra])
	) AS upvt
```

---
Tags: 

Reference:

Related:


| Name | Level | Total |
| ---- | ----- | ----- |
| Joe  | Low   | 34    |
| Joe  | Med   | 65    |
| Joe  | High  | 29    |
| Joe  | Ultra | 99    |
| Tom  | Low   | 37    |
| Tom  | Med   | 53    |
| Tom  | High  | 24    |
| Tom  | Ultra | 74    |

^ccac61

| Name | Low | Med | High | Ultra |
| ---- | --- | --- | ---- | ----- |
| Joe  | 34  | 65  | 29   | 99    |
| Tom  | 37  | 53  | 24   | 74    |

^5c0e2c
