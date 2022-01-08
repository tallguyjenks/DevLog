---
tags: 💻️/TSQL 
publish: true
aliases:
  - 
cssclass: 
created: 2022-01-07 1713
updated: 2022-01-07 1714
---

# [[T-SQL IF ELSE Statements]]

---

Conditional operations. Useful with control [[T-SQL Variables|Variables]]:

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

---

- Tags: 
	- 
- Reference:
	- 
- Related:
	- [[C++ If Else Statements]]
	- [[Bash IF Statements]]
