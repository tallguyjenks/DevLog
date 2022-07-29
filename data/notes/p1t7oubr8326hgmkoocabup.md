
## Syntax

```sql
WHILE CONDITION
BEGIN
   CODE
   BREAK --Optional
   CONTINUE --Optional
END
```

```sql
WHILE (SELECT SUM([OrderQty]) FROM #SalesOrderDetail ) < 300000
BEGIN 
   UPDATE #SalesOrderDetail SET [OrderQty] = [OrderQty] + 1000
 
   IF (SELECT MAX(OrderQty) FROM #SalesOrderDetail) > 3000
      BREAK
   ELSE
      CONTINUE
END
```

```sql
DECLARE @counter INT = 0

WHILE ( @counter <= 5 )
BEGIN
	PRINT 'Too much for the market to bear'
	PRINT '@counter value is:' + CAST(@counter AS VARCHAR)
	SET @counter = @counter + 1
END ;
```

## While Example

```sql
DECLARE @count smallint = 0

WHILE @count<100
BEGIN
  INSERT INTO #email VALUES(@count,CONCAT('user',FLOOR(RAND()*1000),'@outlook.com'))
  SET @count=@count+1
END
```

`WHILE` is not as efficient as [[s.q.tsql.dbos.common-table-expressions]]

## CTE Example

```sql
WITH numbergenerator (id, email) AS
(
   SELECT 1 AS id, CONCAT('user',floor(1000*RAND(CHECKSUM(NEWID()))),'@outlook.com') as email
   UNION ALL
   SELECT ng.id + 1  AS id, CONCAT('user',floor(1000*RAND(CHECKSUM(NEWID()))),'@outlook.com')
   FROM numbergenerator ng
   WHERE ng.id < 100
)
SELECT  *
INTO #numbergenerator
FROM numbergenerator ng;
GO
```


