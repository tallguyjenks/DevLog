---
id: s3d373tpnwdmwg0xf7ohj5z
title: Pivots
desc: ''
updated: 1641413891718
created: 1641105063936
stub: false
isDir: false
---

## Pivoting

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

## UN-pivoting

```sql
SELECT Name
	,upvt.Level
	,upvt.Total
FROM Person
UNPIVOT
	(Total FOR Level IN ([Low], [Med], [High], [Ultra])
	) AS upvt
```

## Advanced Pivoting

<https://www.mssqltips.com/sqlservertip/7167/sql-pivot-grouping-sets-advanced-reporting/>
