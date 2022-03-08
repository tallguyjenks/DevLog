---
id: r6o2tqpirghkz82sdm0dmwo
title: Truncate
desc: ''
updated: 1641414150879
created: 1641105063939
stub: false
isDir: false
---


`TRUNCATE` Allows us to delete all rows from a table without removing the table from the database

```sql
TRUNCATE TABLE My_Table
```

<em>\*</em>`TRUNCATE` is minimally logged and will perform far faster than [[T-SQL DELETE|s.q.tsql.syntax.dml.delete]] will.
