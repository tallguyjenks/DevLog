---
id: e4ppwz3sbf2o28o3eg2lm4t
title: Drop
desc: ''
updated: 1641413120113
created: 1641105063934
stub: false
isDir: false
---


`DROP TABLE` lets us Delete a table from a data base not just its data like [[T-SQL TRUNCATE|s.q.tsql.dml.truncate]] or [[T-SQL DELETE|s.q.tsql.dml.delete]]. Can add `IF EXISTS` starting from SQL Server 2016. cannot drop a table that is referenced by a foreign key constraint.

```sql
drop TABLE My_Table
-- OR
drop TABLE IF EXISTS My_Table
```

Similar to [[s.q.tsql.temp-tables]] dropping where `IF NOT NULL` is similar to `IF EXISTS`:

![[s.q.tsql.temp-tables]]
