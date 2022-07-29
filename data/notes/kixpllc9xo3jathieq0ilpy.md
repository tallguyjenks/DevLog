

Neat way to use TOP to delete / truncate

Deleting a large table takes a lot of resources and causes a lot of locks

Looping query that deletes 100k rows per iteration until 0 rows remain

When using TOP with a DELETE statement, you have to use the new syntax - using "( )" parenthesis

Allows us to delete a very large table without using a lot of peak resources

Deletes in chunks, allows parts to be deleted, very handy technique

```sql
-- do delete in chunks to minimize max lock/resources
updateMore:
DELETE TOP(100000) DB.dbo.big_table
IF @@rowcount !=0
goto updateMore;
```
