---
id: y7bhq8aufi79ze26my9nn7m
title: Local
desc: ''
updated: 1646345181253
created: 1646345181253
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
