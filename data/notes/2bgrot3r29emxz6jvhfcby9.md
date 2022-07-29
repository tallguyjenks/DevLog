

- [[s.q.tsql]] [Renaming SQL Server database objects and changing object owners][1]
  - Rename a database with `sp_renamedb` or `sp_rename`

## Example: rename database from Test1 to Test2

```sql
ALTER DATABASE [Test1] MODIFY NAME = [Test2]
--or
sp_renamedb 'Test1' , 'Test2
--or
sp_rename 'Test1', 'Test2', 'DATABASE';
```

- This could be any object that exists with SQL Server table, stored procedure, trigger, etc.

## Example: rename object Test1 to Test2.

```sql
sp_rename 'dbo.Test1', 'Test2', 'OBJECT';
```

-  [[s.l.python]] [[s.l.python.libs.mito]] [[s.l.python.libs.lux]] [3 Python Packages that make Data Science Simple][2]

[1]: https://www.mssqltips.com/sqlservertip/1396/renaming-sql-server-database-objects-and-changing-object-owners/?utm_source=feedburner&utm_medium=feed&utm_campaign=Feed%3A+MSSQLTips-LatestSqlServerTips+%28MSSQLTips+-+Latest+SQL+Server+Tips%29
[2]: https://medium.com/analytics-vidhya/3-python-packages-that-make-data-science-simple-40744de22592
