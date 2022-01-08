---
tags: 💻️/TSQL 
publish: true
aliases:
  - 
cssclass: 
created: 2022-01-07 1712
updated: 2022-01-07 1713
---

# [[T-SQL Select Data Into JSON]]

---

```sql
SELECT TOP (1000) *
  FROM [DataBase].[schema].[table] AS t
  FOR JSON PATH, ROOT('RootNode')
```

---

- Tags: 
	- 
- Reference:
	- [Reference Docs](https://docs.microsoft.com/en-us/sql/relational-databases/json/format-query-results-as-json-with-for-json-sql-server?view=sql-server-ver15)
- Related:
	- [[Python JSON]]
