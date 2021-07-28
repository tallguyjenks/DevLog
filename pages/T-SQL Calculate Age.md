---
tags:
#  - 🌱️
#  - 🌞️
#  - 🌲️
aliases: 
  - 
cssclass: 
---

#### [[T-SQL Calculate Age]]

---

```sql
-- The '365.25' uses .25 to account for leap year
FLOOR(DATEDIFF(DAY, <birthdate>, GETDATE())/365.25) AS Age
```

---
Tags: 

Reference:

Related:
- 
