
> Cursors are a really inefficient way to loop, so they should only be used in those cases where your process is so inefficient that a cursor is the only thing less efficient than your process. A good example of this is loading large amounts of data between tables.

```sql
USE demo

DECLARE @Year INT
DECLARE @Month INT

DECLARE BatchingCursor CURSOR FOR
SELECT DISTINCT YEAR([SomeDateField]),MONTH([SomeDateField])
FROM [Sometable];


OPEN BatchingCursor;
FETCH NEXT FROM BatchingCursor INTO @Year, @Month;
WHILE @@FETCH_STATUS = 0
BEGIN

BEGIN TRANSACTION
--All logic goes in here
--Any select statements from [Sometable] need to be suffixed with:
--WHERE Year([SomeDateField])=@Year AND Month([SomeDateField])=@Month   
COMMIT TRANSACTION

FETCH NEXT FROM BatchingCursor INTO @Year, @Month;
END;
CLOSE BatchingCursor;
DEALLOCATE BatchingCursor;
GO
```


