---
tags:
#  - 🌱️
#  - 🌞️
#  - 🌲️
aliases: 
  - UPDATE
  - UPDATE TABLE
cssclass: 
---

#### [[T-SQL UPDATE]]

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

uses elements:
- [[T-SQL Begin Transaction|Begin Tran]]
- [[T-SQL Rollback|Rollback]]
- [[T-SQL Commit|Commit]]
- [OUTPUT](https://docs.microsoft.com/en-us/sql/t-sql/queries/output-clause-transact-sql?view=sql-server-ver15)

| BEFORE        | AFTER  |
| ------------- | ------ |
| ![[#^4300e5]] | ![[#^f325e1]] |
|               |        |

---
Tags: 

Reference:

Related:


| ID  | Name | Misc   |
| --- | ---- | ------ |
| 1   | AAA  | First  |
| 2   | BBB  | Second |
| 3   | CCC  | Third  |
| 4   | DDD  | **NULL**   |

^4300e5

| ID  | Name | Misc   |
| --- | ---- | ------ |
| 1   | AAA  | First  |
| 2   | BBB  | Second |
| 3   | CCC  | Third  |
| 4   | DDD  | Fourth   |

^f325e1
