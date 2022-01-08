---
tags: 💻️/TSQL 
publish: true
aliases:
  - 
cssclass: 
created: 2022-01-07 1723
updated: 2022-01-07 1723
---

# [[T-SQL Cross Join]]

---

A Cartesian Product that matches every unique value from one table to every unique value on another table for the complete list of every unique pairing:

| Table 1       | Table 2       | Result        |
| ------------- | ------------- | ------------- |
| ![[#^6f95be]] | ![[#^af59ca]] | ![[#^b03005]] |


| Table | One |
| ----- | --- |
| 1     | A   | 
| 2     | B   |

^6f95be

| Table | Two |
| ----- | --- |
| 1     | C   |
| 2     | D   |

^af59ca

| Result | Table |
| ------ | ----- |
| 1      | AC    |
| 2      | AD    |
| 3      | BC    |
| 4      | BD    |

^b03005

---

- Tags: 
	- 
- Reference:
	- 
- Related:
	- 
