---
id: oUORTLZY9iyvRxNN6F4eu
title: Chaining
desc: ''
updated: 1641597850997
created: 1641412852683
---

### Chaining CTE's:

```sql
WITH My_Table (Age, Counts)
AS
(
	SELECT Age, COUNT(Name) AS Counts
	FROM Source_Table
	WHERE Age > 55
	GROUP BY Age
), -- THE COMMA IS THE IMPORTANT PART OF THIS CHAINING
My_Second_CTE
AS
(
	SELECT Age, Counts, Average(Counts)
	FROM My_Table
	ORDER BY Age
	GROUP BY Age, Counts
)

SELECT * FROM My_Second_CTE

```

CTE's are often faster than [[T-SQL Temp Tables|s.q.tsql.temp-tables]]
