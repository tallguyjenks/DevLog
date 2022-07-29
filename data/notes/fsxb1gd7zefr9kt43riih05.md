

```sql
( 5.1 ) SELECT 
         ( 5.2 ) DISTINCT 
         ( 7 ) TOP 
( 1 ) FROM  <tables>  [JOIN, APPLY, PIVOT, UNPIVOT]
( 2 ) WHERE
( 3 ) GROUP BY
( 4 ) HAVING
( 6 ) ORDER BY
```

1. `FROM`:  The query process starts with the FROM clause. Beginning with the specified source tables, it processes table operators (join, apply, etc.) in written order from left to right.  
2. `WHERE`: This phase filters the rows based on the predicate in the WHERE clause. Only rows for which the predicate evaluates to TRUE are returned.
3. `GROUP BY`: This phase arranges the filtered rows in groups based on the set of expressions (aka, grouping set) specified in the GROUP BY clause. There will be one result row per qualifying group
4. `HAVING`: This phase filters the groups on the predicate that appears in the HAVING clause (similar to a WHERE clause but for groups). Only groups for which the predicate evaluates to TRUE are returned.
5. `SELECT`
6. `Evaluate Expressions`: This phase evaluates the expressions in the SELECT list.
7. `DISTINCT`: This phase removes duplicate rows from the SELECT list results.
8. `ORDER BY `: This phase orders the rows according to the list in the ORDER BY clause.
9. `TOP`: This phase filters specified number of rows based on the ordering in the ORDER BY clause, or based on arbitrary order if there is no ORDER BY clause specified. 
