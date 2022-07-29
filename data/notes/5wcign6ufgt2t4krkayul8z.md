

**Best Practice**

`BEGIN TRAN` marks the beginning of a local transaction and is not recorded until [[T-SQL Commit|committed]]. This allows us to [[T-SQL Rollback|s.q.tsql.syntax.tcl.rollback]] any unwanted transactions. 

Best practice is to use [[T-SQL Begin Transaction|begin-tran]] to start especially when using the following [[T-SQL Data Manipulation Language|dml]] commands: `INSERT`, `DELETE`, & `UPDATE`

```sql
BEGIN TRAN
	INSERT INTO Database.Schema.Table (<field>)
	VALUES('<INSERTED VALUE>')
	
	SELECT *
	FROM Database.Schema.Table
ROLLBACK
COMMIT
```
