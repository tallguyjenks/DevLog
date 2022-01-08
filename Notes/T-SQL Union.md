---
tags: 💻️/TSQL 
publish: true
aliases:
  - 
cssclass: 
created: 2022-01-07 1724
updated: 2022-01-07 1725
---

# [[T-SQL Union]]

---


The `UNION` Operator us useful for combining the records from one table to another.

There must be:
- Same number of columns in both tables
- columns must align with each other and be the same data type

the operator basically does this: 

| TABLE 1       | TABLE 2       | UNION         |
| ------------- | ------------- | ------------- |
| ![[#^17b500]] | ![[#^912344]] | ![[#^708f69]] |

```sql
SELECT ID, Value
FROM My_First_Table
UNION
SELECT ID, Value
FROM My_Second_Table
```

| ID  | Val |
| --- | --- |
| 1   | A   |
| 2   | B   |

^17b500

| ID  | Val |
| --- | --- |
| 3   | C   |
| 4   | D   |

^912344

| ID  | Val |
| --- | --- |
| 1   | A   |
| 2   | B   |
| 3   | C   |
| 4   | D   |

^708f69


---

- Tags: 
	- 
- Reference:
	- 
- Related:
	- 
