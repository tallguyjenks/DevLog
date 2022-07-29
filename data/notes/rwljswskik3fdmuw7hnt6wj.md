

With case statements in T-SQL you can in essence insert a bunch of logic and calculation into a multi-faceted case statement with the output being a single result field

```sql
SELECT P.Age
		,CASE
			WHEN P.Age > 55	THEN 1
			ELSE 0
		END AS 'RetirementAge'
FROM Person AS P
```

This case statement examines the `Age` field and asks if each value i `> 55` if it is, the result field is assigned a `1` if `Age` is not `> 55` then the `ELSE` statement is executed and the result field receives the value of `0`. 

The ultimate of this being a boolean flag column indicating if each individual is at `RetirementAge` or not. 

You can also nest several `WHEN ... THEN` statements for a multi faceted Case statement:

```sql
SELECT P.Age
		,CASE
			WHEN P.Age > 65	THEN 'Senior Citizen'
			WHEN P.Age > 55	THEN 'Mature Adult'
			WHEN P.Age > 40	THEN 'Mid-Life Crisis'
			ELSE 'No Discount'
		END AS 'DiscountLevel'
FROM Person AS P
```
