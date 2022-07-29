
```sql
USE demo

DECLARE @OperatorName sysname = N'YourOperatorName';

DECLARE @OperatorEmailAddress nvarchar(100) = (SELECT email_address FROM msdb.dbo.sysoperators WHERE [name] = @OperatorName);

PRINT @OperatorEmailAddress
```
