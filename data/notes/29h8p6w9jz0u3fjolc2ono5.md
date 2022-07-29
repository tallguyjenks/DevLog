
- <https://docs.microsoft.com/en-us/sql/relational-databases/system-catalog-views/sys-objects-transact-sql?view=sql-server-ver15>

```sql
USE AdventureWorks2012;
GO
IF EXISTS OBJECT_ID(N'dbo.AWBuildVersion', N'U')
    DROP TABLE dbo.AWBuildVersion;
GO
```

The additional types at the end can be found at the documentation link above
