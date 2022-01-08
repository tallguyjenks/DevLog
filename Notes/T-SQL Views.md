---
tags: 💻️/TSQL 
publish: true
aliases:
  - 
cssclass: 
created: 2022-01-07 1722
updated: 2022-01-07 1723
---

# [[T-SQL Views]]

---

In SQL, a view is a virtual table based on the result-set of an SQL statement. A view contains rows and columns, just like a real table. The fields in a view are fields from one or more real tables in the database.

Views can be used when we you need a physical table but query a certain table with certain criteria often, you can use a view for this.

can be queried like most normal tables:

```sql
SELECT *
FROM v_view
```

### Creating a view

![[Pasted image 20201216004040.png]]

![[Pasted image 20201216004102.png]]

---

- Tags: 
	- 
- Reference:
	- 
- Related:
	- [[T-SQL Stored Procedures|Stored Procedures]]
