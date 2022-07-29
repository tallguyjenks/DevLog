
For loops do not exist in SQL Server so here's how to replicate them with a [[s.q.tsql.flow.loops.while]] loop.

```sql
DECLARE @cnt INT = 0;

WHILE @cnt < cnt_total
BEGIN
   {...statements...}
   SET @cnt = @cnt + 1;
END;
```
