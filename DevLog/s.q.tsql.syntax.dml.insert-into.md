---
id: rqg3dipq9eb4hg19cnl8k5x
title: Insert Into
desc: ''
updated: 1641597434896
created: 1641105063935
stub: false
isDir: false
---


```sql
INSERT INTO database.schema.table (<col1>, <col2>, <col3>) VALUES
  (<val1>, <val2>, <val3>)
, (<val1>, <val2>, <val3>)
, (<val1>, <val2>, <val3>)r
-- OR
INSERT INTO database.schema.table
SELECT <columns>
FROM <other_table>
```

`INSERT INTO` is also used with temp table creation:

![[s.q.tsql.dbos.temp-tables]]
