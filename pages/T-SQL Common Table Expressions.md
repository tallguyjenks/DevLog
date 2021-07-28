---
tags:
aliases: 
  - CTE
  - Common Table Expression
  - Common Table Expressions
cssclass: 
---

#### [[T-SQL Common Table Expressions]]

---

A `CTE` is a temporary result set that you can reference within another `SELECT`, [[T-SQL INSERT INTO|INSERT]], [[T-SQL UPDATE|UPDATE]], or [[T-SQL DELETE|DELETE]] statement.

A `CTE` always returns a result set. They are used to simplify queries, like eliminating a derived table from the main query body:

```sql
WITH My_Table (Age, Counts)
AS
(
	SELECT Age, COUNT(Name) AS Counts
	FROM Source_Table
	WHERE Age > 55
	GROUP BY Age
)
SELET *
FROM My_Table
ORDER BY Age
GO
```

No [[T-SQL Temp Tables|Temp Table]] assignment, no need to make an intermediary table. I like to this of `CTE`'s like Rice paddy fields where the data like the water just flows downward into the next query or `CTE`.

![[Pasted image 20210501114105.png]]

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
	SELET Age, Counts, Average(Counts)
	FROM My_Table
	ORDER BY Age
	GROUP BY Age, Counts
)

SELECT * FROM My_Second_CTE

```

CTE's are often faster than [[T-SQL Temp Tables|Temp Tables]]

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

---
Tags: 

Reference:

Related:
- 
