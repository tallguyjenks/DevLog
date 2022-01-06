---
id: BMeUWH8rUC7EoQuhrF0Iq
title: Insert Into
desc: ''
updated: 1641413252848
created: 1641105063935
stub: false
isDir: false
---

```sql
INSERT INTO database.schema.table (<col1>, <col2>, <col3>)
		VALUES (<val1>, <val2>, <val3>)
-- OR
INSERT INTO database.schema.table
SELECT <columns>
FROM <other_table>
```

`INSERT INTO` is also used with temp table creation:

![[s.q.tsql.temp-tables]]
