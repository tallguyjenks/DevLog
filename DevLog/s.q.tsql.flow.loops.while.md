---
id: x311wpv1e5tqcamw2zlj3qt
title: While
desc: ''
updated: 1641414277168
created: 1641105063940
stub: false
isDir: false
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
