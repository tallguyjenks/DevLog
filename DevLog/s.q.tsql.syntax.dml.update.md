---
id: b5r287mgun7e7pljwbn2tdn
title: Update
desc: ''
updated: 1641414254981
created: 1641105063939
stub: false
isDir: false
---


`UPDATE` Allows us to update a set of data in a table that can be specified by the `WHERE` criteria.

```sql
UPDATE My_Table
SET <Column1> = [updated_value1]
	,<Column2> = [updated_value2]
	,[...]
WHERE <filter(s)> (Optional)
```

So in essence:

```sql
BEGIN TRAN
UPDATE database.schema.table
SET Misc = 'Fourth'
OUTPUT Inserted.*
WHERE ID = 4

SELECT * FROM database.schema.table
ROLLBACK COMMIT
```

- Uses elements:
  - [[s.q.tsql.syntax.tcl.begin-transaction]]
  - [[T-SQL Rollback|s.q.tsql.syntax.tcl.rollback]]
  - [[T-SQL Commit|s.q.tsql.syntax.tcl.commit]]
  - [OUTPUT](https://docs.microsoft.com/en-us/sql/t-sql/queries/output-clause-transact-sql?view=sql-server-ver15)

