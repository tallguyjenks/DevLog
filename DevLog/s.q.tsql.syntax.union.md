---
id: zoxpeno0nw2w1pkau7cmnwq
title: Union
desc: ''
updated: 1646689345652
created: 1641105063939
stub: false
isDir: false
---


The `UNION` Operator us useful for combining the records from one table to another.

There must be:

- Same number of columns in both tables
- columns must align with each other and be the same data type

the operator basically does this:

```sql
SELECT ID, Value
FROM My_First_Table
UNION
SELECT ID, Value
FROM My_Second_Table
```
