

Similar to [[s.q.tsql.syntax.between-predicate]], the `IN` predicate denotes not a range between value A and B but any value in a list that doesnt lend itself to ranging like specific text values or disjointed numerical values:

```sql
SELECT Age
FROM Person
WHERE Age IN (55, 65, 80) -- This matches only to those 3 listed numbers

-- OR

SELECT Name
FROM Person
WHERE Name IN ('Bob', 'Joe', 'Mary', 'Sue') -- matching on strings
```
