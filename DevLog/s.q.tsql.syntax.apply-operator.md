---
id: vjsd28084b4x7kgpw46crxo
title: Apply Operator
desc: ''
updated: 1641412756637
created: 1641105063931
stub: false
isDir: false
---


`CROSS APPLY` = [[T-SQL Inner Join|s.q.tsql.syntax.joins.inner-join]]

```sql
SELECT *
FROM Department D
CROSS APPLY (
    SELECT *
    FROM Employee E
    WHERE E.DepartmentID = D.DepartmentID
) A

-- The result sets from these would have been identical

SELECT *
FROM Department D
INNER JOIN Employee E
  ON D.DepartmentID = E.DepartmentID
```

`OUTER APPLY` = [[T-SQL Left Join|s.q.tsql.syntax.joins.left-join]]

```sql
SELECT *
FROM Department D
OUTER APPLY (
    SELECT *
    FROM Employee E
    WHERE E.DepartmentID = D.DepartmentID
) A


-- The result sets from these would have been identical

SELECT *
FROM Department D
LEFT OUTER JOIN Employee E
  ON D.DepartmentID = E.DepartmentID
```

Great uses for Apply

- [SO Examples for apply](https://stackoverflow.com/questions/9275132/real-life-example-when-to-use-outer-cross-apply-in-sql)
- [Examples of main use cases](https://riptutorial.com/sql/example/8323/cross-apply-and-outer-apply-basics)
