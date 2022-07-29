

An inner join is the default join in T-SQL. The `INNER` is optional but it is a best practice to use it.

````sql
```sql
SELECT M.Age, F.Age -- 2 Columns called 'Age' are returned because of the alias prefix
FROM MENS_AGES AS M
	[INNER] JOIN WOMENS_AGES AS F
		ON F.Marriage_ID = M.Marriage_ID
WHERE M.Age > 55 AND F.Age > 55
````

The `INNER JOIN` returns records where the criteria being joined upon matches on both tables

If you have a table with Men
and a table with Women

and want to `INNER JOIN` and return the married couples across both tables

you'd likely `INNER JOIN` Men to Women on `MARRIAGE_ID` and only the pairs with ID's matching each other will be returned. This means that single people in either table will not be returned at all. _Sorry!_
