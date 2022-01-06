---
id: AesUYHUCOrkA29ZEcSaPQ
title: If Else Statements
desc: ''
updated: 1641413216106
created: 1641105063935
stub: false
isDir: false
---

Conditional operations. Useful with control [[T-SQL Variables|s.q.tsql.variables]]:

```sql
DECLARE @retirement INT = 1 -- Using a binary flag

if @retirement = 1
	BEGIN
		SELECT *
		FROM My_Table
		WHERE Retirement = 1
	END
ELSE
	BEGIN
		SELECT *
		FROM My_Table
		WHERE Retirement = 0
	END
```
