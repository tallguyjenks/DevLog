

`TRUNCATE` Allows us to delete all rows from a table without removing the table from the database

```sql
TRUNCATE TABLE My_Table
```

<em>\*</em>`TRUNCATE` is minimally logged and will perform far faster than [[T-SQL DELETE|s.q.tsql.syntax.dml.delete]] will.
