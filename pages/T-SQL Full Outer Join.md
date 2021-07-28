---
tags:
#  - 🌱️
#  - 🌞️
#  - 🌲️
aliases: 
  - Full Outer Join
cssclass: 
---

#### [[T-SQL Full Outer Join]]

---

This joins preserves both tables and retains all records but where there are matches it links them up

| Table 1       | Table 2       | Result        |
| ------------- | ------------- | ------------- |
| ![[#^e542c8]] | ![[#^5062ac]] | ![[#^ae30ae]] 

---
Tags: 

Reference:

Related:



| Table | One |
| ----- | --- |
| 1     | A   |
| 2     | B   |
| 3     | C   |
| 4     | D    |

^e542c8



| Table | Two  |
| ----- | ---- |
| 1     | C    |
| 2     | D    |
| 3     | NULL |
| 4     | NULL |
| 5     | E    |
| 6     | F    |

^5062ac



| Result | Table One | Table Two |
| ------ | --------- | --------- |
| 1      | A         | C         |
| 2      | B         | D         |
| 3      | C         | NULL      |
| 4      | D         | NULL      |
| 5      | NULL      | E         |
| 6      | NULL      | F         |

^ae30ae


