
## Disable

### Blanket Disable

```sql
USE MSDB;
GO

DECLARE @job_id uniqueidentifier

DECLARE job_cursor CURSOR READ_ONLY FOR
SELECT job_id FROM msdb.dbo.sysjobs WHERE enabled = 1

OPEN job_cursor
FETCH NEXT FROM job_cursor INTO @job_id

WHILE @@FETCH_STATUS = 0
BEGIN
   EXEC msdb.dbo.sp_update_job @job_id = @job_id, @enabled = 0
   FETCH NEXT FROM job_cursor INTO @job_id
END

CLOSE job_cursor
DEALLOCATE job_cursor
```

### Disable by name

```sql
USE MSDB;
GO

DECLARE @job_id uniqueidentifier

DECLARE job_cursor CURSOR READ_ONLY FOR
SELECT job_id FROM msdb.dbo.sysjobs WHERE enabled = 1 AND [name] like N'Admin%'

OPEN job_cursor
FETCH NEXT FROM job_cursor INTO @job_id

WHILE @@FETCH_STATUS = 0
BEGIN
   EXEC msdb.dbo.sp_update_job @job_id = @job_id, @enabled = 0
   FETCH NEXT FROM job_cursor INTO @job_id
END

CLOSE job_cursor
DEALLOCATE job_cursor
```

### Disable Jobs By Job Category

```sql
USE MSDB;
GO

DECLARE @job_id uniqueidentifier

DECLARE job_cursor CURSOR READ_ONLY FOR
SELECT SJ.job_id
FROM msdb.dbo.sysjobs SJ
   INNER JOIN msdb.dbo.syscategories AS SC
      ON SJ.category_id = SC.category_id
WHERE SJ.enabled = 1
   AND SC.[name] = N'Database Maintenance'

OPEN job_cursor
FETCH NEXT FROM job_cursor INTO @job_id

WHILE @@FETCH_STATUS = 0
BEGIN
   EXEC msdb.dbo.sp_update_job @job_id = @job_id, @enabled = 0
   FETCH NEXT FROM job_cursor INTO @job_id
END

CLOSE job_cursor
DEALLOCATE job_cursor
```

## Enable

```sql
USE MSDB;
GO

DECLARE @job_id uniqueidentifier

DECLARE job_cursor CURSOR READ_ONLY FOR
SELECT job_id FROM msdb.dbo.sysjobs WHERE enabled = 0

OPEN job_cursor
FETCH NEXT FROM job_cursor INTO @job_id

WHILE @@FETCH_STATUS = 0
BEGIN
   EXEC msdb.dbo.sp_update_job @job_id = @job_id, @enabled = 1
   FETCH NEXT FROM job_cursor INTO @job_id
END

CLOSE job_cursor
DEALLOCATE job_cursor
```
