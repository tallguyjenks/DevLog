---
id: tguVBezqMmnpFu8TBJCCg
title: Yyyymm Date Part Calculation
desc: ''
updated: 1641414296650
created: 1641105063940
stub: false
isDir: false
---

```sql
SELECT DATEPART(YEAR, GETDATE()) * 100 + DATEPART(MONTH, GETDATE()) AS 'YearMo'
```
