

In SQL, a view is a virtual table based on the result-set of an SQL statement. A view contains rows and columns, just like a real table. The fields in a view are fields from one or more real tables in the database.

Views can be used when we you need a physical table but query a certain table with certain criteria often, you can use a view for this.

can be queried like most normal tables:

```sql
SELECT *
FROM v_view
```

