---
id: 29h8p6w9jz0u3fjolc2ono5
title: Object_id
desc: ''
updated: 1648069672359
created: 1648069601138
---

- <https://docs.microsoft.com/en-us/sql/relational-databases/system-catalog-views/sys-objects-transact-sql?view=sql-server-ver15>

```sql
USE AdventureWorks2012;
GO
IF EXISTS OBJECT_ID(N'dbo.AWBuildVersion', N'U')
    DROP TABLE dbo.AWBuildVersion;
GO
```

The additional types at the end can be found at the documentation link above
