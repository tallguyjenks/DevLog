

### Recursive CTE

Useful when you dont have a defined number of iterations

```sql
WITH CTE
AS
(
	SELECT 1 AS n -- Anchor Member
	UNION ALL
	SELECT n + 1 -- Recursive Member
	FROM CTE
	WHERE n < 50 -- Terminator
)
SELECT n 
FROM CTE;
```
