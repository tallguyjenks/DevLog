

<https://www.mssqltips.com/sqlservertip/1476/how-to-read-log-file-in-sql-server-using-tsql/>

## How to Read Log File in SQL Server using TSQL

### Problem

> One of the issues I have is that the SQL Server Error Log is quite large and it is not always easy to view the contents with the Log File Viewer. In a previous tip "Simple way to find errors in SQL Server error log" you discussed a method of searching the error log. Are there any other ways to search and find errors in the error log files?

### Solution

> SQL Server offers an undocumented system stored procedure `sp_readerrorlog`. This SP allows you to read the contents of the SQL Server error log files directly from a query window and also allows you to search for certain keywords when reading the error file.
>
> This is a sample of the stored procedure that already exists in the master database. You will see that when this gets called it calls an extended stored procedure `xp_readerrorlog`.

```sql
/*
This procedure takes four parameters:

1. Value of error log file you want to read: 0 = current, 1 = Archive #1, 2 = Archive #2, etc...
2. Log file type: 1 or NULL = error log, 2 = SQL Agent log
3. Search string 1: String one you want to search for
4. Search string 2: String two you want to search for to further refine the results

If you do not pass any parameters this will return the contents of the current error log.
*/

CREATE PROC [sys].[sp_readerrorlog](
   @p1 INT = 0,
   @p2 INT = NULL,
   @p3 VARCHAR(255) = NULL,
   @p4 VARCHAR(255) = NULL)
AS
BEGIN

   IF (NOT IS_SRVROLEMEMBER(N'securityadmin') = 1)
   BEGIN
      RAISERROR(15003,-1,-1, N'securityadmin')
      RETURN (1)
   END

   IF (@p2 IS NULL)
       EXEC sys.xp_readerrorlog @p1
   ELSE
       EXEC sys.xp_readerrorlog @p1,@p2,@p3,@p4
END
```

The above is basically a copy of `xp_readerrorlog` but only using 4 of the parameters

The actual extended procedure `xp_readerrorlog` can take up to 7 parameters

1. Value of error log file you want to read: 0 = current, 1 = Archive #1, 2 = Archive #2, etc...
2. Log file type: 1 or NULL = error log, 2 = SQL Agent log
3. Search string 1: String one you want to search for
4. Search string 2: String two you want to search for to further refine the results
5. Search from start time
6. Search to end time
7. Sort order for results: N'asc' = ascending, N'desc' = descending

Here is are some examples:

```sql
EXEC master.dbo.xp_readerrorlog 0, 1, '2005', 'exec', NULL, NULL, N'desc'
EXEC master.dbo.xp_readerrorlog 0, 1, '2005', 'exec', NULL, NULL, N'asc'
```

## Potential pitfalls

> for later versions of SQL Server you may need to use double quotes or you might get this error.

`Msg 22004, Level 12, State 1, Line 0
Error executing extended stored procedure: Invalid Parameter Type`

Try this instead.

```sql
EXEC master.dbo.xp_readerrorlog 0, 1, "backup", "failed", "2017-01-02", "2017-02-02", "desc"
EXEC master.dbo.xp_readerrorlog 0, 1, "2005", "exec", NULL, NULL, "asc"
```

Or try this, putting N before each parameter.

```sql
EXEC master.dbo.xp_readerrorlog 0, 1, N'backup', NULL, N'2017-01-02', N'2017-02-02', N'desc'
EXEC master.dbo.xp_readerrorlog 0, 1, N'backup', N'failed', NULL, NULL, N'asc'
```
