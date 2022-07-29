

Conditional operations. Useful with control [[T-SQL Variables|s.q.tsql.syntax.variables]]:

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
