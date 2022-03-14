---
id: p1t7oubr8326hgmkoocabup
title: While
desc: ''
updated: 1641414277168
created: 1641105063940
stub: false
isDir: false
---

## Syntax

```sql
WHILE CONDITION
BEGIN
   CODE 
   BREAK --Optional 
   CONTINUE --Optional 
END	
```

## Example

```sql
DECLARE @counter INT = 0

WHILE ( @counter <= 5 )
BEGIN
	PRINT 'Too much for the market to bear'
	PRINT '@counter value is:' + CAST(@counter AS VARCHAR)
	SET @counter = @counter + 1
END ;
```

`WHILE` is not as efficient as [[s.q.tsql.dbos.common-table-expressions]]


