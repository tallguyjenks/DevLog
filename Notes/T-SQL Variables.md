---
tags: 💻️/TSQL 
publish: true
aliases:
  - 
cssclass: 
created: 2022-01-07 1719
updated: 2022-01-07 1720
---

# [[T-SQL Variables]]

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

---

- Tags: 
	- 
- Reference:
	- 
- Related:
	- [[Bash Variables]]
	- [[C++ Variables and Datatypes]]
