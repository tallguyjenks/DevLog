

Aliasing a table is to reduce the amount of typing needed for a query. This allows for something like `A_REALLY_LONG_TABLE_NAME` to be reduced to `T` by using an alias:

```sql
SELECT T.Age
FROM A_REALLY_LONG_TABLE_NAME AS T
WHERE T.Age > 55
```

Aliasing allows you to include fields with the same name but different tables:

```sql
SELECT M.Age, F.Age -- 2 Columns called 'Age' are returned because of the alias prefix
FROM MENS_AGES AS M
	JOIN WOMENS_AGES AS F
		ON F.Marriage_ID = M.Marriage_ID
WHERE M.Age > 55 AND F.Age > 55
```
