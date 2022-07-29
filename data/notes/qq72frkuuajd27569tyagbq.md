
```sql
ALTER TABLE dbo.Table
ADD CONSTRAINT Constraint_Name DEFAULT GETDATE() FOR UploadedToSQL
```

if just adding this in the initial table definition you can just define a table as:

```sql
UploadedToSQL DATETIME NOT NULL DEFAULT GETDATE(),
```

and on inserts for that column just pass the value `DEFAULT`
