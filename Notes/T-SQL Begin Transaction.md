---
tags: 💻️/TSQL 
publish: true
aliases:
  - 
cssclass: 
created: 2022-01-07 1722
updated: 2022-01-07 1723
---

# [[T-SQL Begin Transaction]]

---

**Best Practice**

`BEGIN TRAN` marks the beginning of a local transaction and is not recorded until [[T-SQL Commit|Committed]]. This allows us to [[T-SQL Rollback|Rollback]] any unwanted transactions. 

Best practice is to use [[T-SQL Begin Transaction|Begin Tran]] to start especially when using the following [[T-SQL Data Manipulation Language|DML]] commands: `INSERT`, `DELETE`, & `UPDATE`

```sql
BEGIN TRAN
	INSERT INTO Database.Schema.Table (<field>)
	VALUES('<INSERTED VALUE>')
	
	SELECT *
	FROM Database.Schema.Table
ROLLBACK
COMMIT
```

---

- Tags: 
	- 
- Reference:
	- 
- Related:
	- 
