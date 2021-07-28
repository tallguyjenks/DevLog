---
tags:
#  - 🌱️
#  - 🌞️
#  - 🌲️
aliases: 
  - DROP
  - DROP TABLE
cssclass: 
---

#### [[T-SQL DROP]]

---

`DROP TABLE` lets us Delete a table from a data base not just its data like [[T-SQL TRUNCATE|TRUNCATE]] or [[T-SQL DELETE|DELETE]]. Can add `IF EXISTS` starting from SQL Server 2016. cannot drop a table that is referenced by a foreign key constraint.

```sql
drop TABLE My_Table
-- OR
drop TABLE IF EXISTS My_Table
```

Similar to [[T-SQL Temp Tables|Temp Table]] dropping where `IF NOT NULL` is similar to `IF EXISTS`:

![[T-SQL Temp Tables#Usage|Temp Table]]

---
Tags: 

Reference:

Related:
- 
