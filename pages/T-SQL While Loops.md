---
tags:
#  - 🌱️
#  - 🌞️
#  - 🌲️
aliases: 
  - While Loop
  - While Loops
cssclass: 
---

#### [[T-SQL While Loops]]

---

```sql
DECLARE @counter INT = 0

WHILE ( @counter <= 5 )
BEGIN
	PRINT 'Too much for the market to bear'
	PRINT '@counter value is:' + CAST(@counter AS VARCHAR)
SET @counter = @counter + 1
END ;
```

---
Tags: 

Reference:

Related:
- [[C++ While Loops]]
- [[Bash Loops]]
- [[Python Loops]]
