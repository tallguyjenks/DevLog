

```sql
CREATE TABLE Database.schema.table_name
(	ID INT PRIMARY KEY IDENTITY(1,1),
	Name VARCHAR(50),
 	Misc VARCHAR(50)
)
```

The primary key here is using the [Identity()](https://docs.microsoft.com/en-us/sql/t-sql/functions/identity-function-transact-sql?view=sql-server-ver15) function.

The default setting is that this table will have a Clustered index

we can override this explicitly with:

```sql
CREATE TABLE Database.schema.table_name
(	ID INT NOT NULL IDENTITY(1,1),
	Name VARCHAR(50),
 	Misc VARCHAR(50)
 	PRIMARY KEY NONCLUSTERED
 	(
		ID ASC
	)
)
```

[MSDN Docs](https://docs.microsoft.com/en-us/sql/relational-databases/indexes/create-clustered-indexes?view=sql-server-ver15) recommend that most situations unless explicitly defined should just use clustered indexes

### Script new table

If creating a new table with similar structure to an existing one, right click the existing table in SSMS `SCRIPT TABLE AS` --> `CREATE TO` --> `NEW QUERY EDITOR WINDOW`
