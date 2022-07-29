

- [[s.apps.microsoft-orchestrator]]  
- [[s.q.tsql]] make a database single user and also cut off other sessions so you can drop it
  
```sql
ALTER DATABASE <DB NANME HERE> SET SINGLE_USER WITH ROLLBACK IMMEDIATE;
```
  
- [SQL SERVER – FIX : Error : 3702 Cannot drop database because it is currently in use.][1]
- [Set a Database to Single-user Mode][2]
- [SQL Server's Auto Update Statistics Async option][3]


[1]: https://blog.sqlauthority.com/2007/12/07/sql-server-fix-error-3702-cannot-drop-database-because-it-is-currently-in-use/
[2]: https://docs.microsoft.com/en-us/sql/relational-databases/databases/set-a-database-to-single-user-mode?view=sql-server-ver15
[3]: https://www.mssqltips.com/sqlservertip/2904/sql-servers-auto-update-statistics-async-option/
