---
tags: 💻️/TSQL 
publish: true
aliases:
  - 
cssclass: 
created: 2022-01-07 1722
updated: 2022-01-07 1722
---

# [[T-SQL Table Aliasing]]

---

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

---

- Tags: 
	- 
- Reference:
	- 
- Related:
	- 
