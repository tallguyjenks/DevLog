
## Link

<https://www.mssqltips.com/sqlservertip/2470/understanding-the-sql-server-nolock-hint/>

## Notes

> What does the SQL Server `NOLOCK` hint do?

1. The `NOLOCK` hint allows SQL to read data from tables by ignoring any locks and therefore not get blocked by other processes.
2. This can improve query performance by removing the blocks, but introduces the possibility of dirty reads.
3. Read further to better understand the use of `NOLOC`K`.

## Dirty Reads

The `NOLOCK` hint is the same as the `READUNCOMMITED` hint and can be used as follows with the same results.

```sql
SELECT * FROM Person.Contact WITH (READUNCOMMITTED)
```

This allows the reading of data that hasnt even been comitted to the database yet.
