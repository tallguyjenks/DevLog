---
tags:
#  - 🌱️
#  - 🌞️
#  - 🌲️
aliases: 
  - YYYYMM
cssclass: 
---

#### [[T-SQL YYYYMM Date Part Calculation]]

---

```sql
SELECT DATEPART(YEAR, GETDATE()) * 100 + DATEPART(MONTH, GETDATE()) AS 'YearMo'
```

---
Tags: 

Reference:

Related:
- 
