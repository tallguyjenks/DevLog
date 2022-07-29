
In your code start your WHERE clause with a `WHERE TRUE` so that all logical statements are in `AND` statement on subsequent lines and therefore more easily commented out.

```sql
SELECT *
FROM dbo.my_table
WHERE TRUE
AND person_id > 5
AND age BETWEEN 18 AND 65
AND first_name LIKE '%Paul%'
```
