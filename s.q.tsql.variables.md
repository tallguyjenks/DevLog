---
id: GYBTXIhqRdIzrIrYGYfFM
title: Variables
desc: ''
updated: 1641414263032
created: 1641105063940
stub: false
isDir: false
---

To declare a variable in T-SQL for reuse throughout a query, the syntax is simple:

```sql
DECLARE @VariableName AS datatype
SET @VariableName = value

-- OR
DECLARE @VariableName AS datatype = value
```

You can also use a single declare to create multiple variable in one go:

```sql
DECLARE @VariableName AS datatype
		,@VariableName2 AS datatype
```
