

`DROP TABLE` lets us Delete a table from a data base not just its data like [[T-SQL TRUNCATE|s.q.tsql.syntax.dml.truncate]] or [[T-SQL DELETE|s.q.tsql.syntax.dml.delete]]. Can add `IF EXISTS` starting from SQL Server 2016. cannot drop a table that is referenced by a foreign key constraint.

```sql
drop TABLE My_Table
-- OR
drop TABLE IF EXISTS My_Table
```

Similar to [[s.q.tsql.dbos.temp-tables]] dropping where `IF NOT NULL` is similar to `IF EXISTS`:

![[s.q.tsql.dbos.temp-tables]]
