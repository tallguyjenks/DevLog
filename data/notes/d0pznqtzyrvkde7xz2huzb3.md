
> Here is a sample T-SQL script that will create the commands for you. This script actually outputs the commands that can then be copied and pasted into a query windows and executed to make the updates. The script could also be changed to automatically issue the commands, but with this version you have the ability to review the commands before you execute them.
>
> -- <https://www.mssqltips.com/sqlservertip/1091/setting-up-alerts-for-all-sql-server-agent-jobs/>

```sql
USE msdb
GO

DECLARE @operator varchar(50)
SET @operator = 'SQLalerts'

SELECT 'EXEC msdb.dbo.sp_update_job @job_ID = ''' + convert(varchar(50),job_id)
        + ''' ,@notify_level_email = 2, @notify_email_operator_name = ''' + @operator + ''''
FROM sysjobs
```

When this gets run the following output is created:

```sql
EXEC msdb.dbo.sp_update_job @job_ID = '589D2B60-EDBD-45B5-BDE6-4DD974D20D25' ,@notify_level_email = 2, @notify_email_operator_name = 'SQLalerts'
EXEC msdb.dbo.sp_update_job @job_ID = '6BE4306C-CC37-4D38-BC27-1B099601EF6A' ,@notify_level_email = 2, @notify_email_operator_name = 'SQLalerts'
EXEC msdb.dbo.sp_update_job @job_ID = 'F7569D9A-641E-4130-90F4-535F0B11FC1E' ,@notify_level_email = 2, @notify_email_operator_name = 'SQLalerts'
EXEC msdb.dbo.sp_update_job @job_ID = 'CD012AF2-BC96-4D9E-A03E-6ABB2F6048AF' ,@notify_level_email = 2, @notify_email_operator_name = 'SQLalerts'
EXEC msdb.dbo.sp_update_job @job_ID = '451C94B4-8BA3-48AA-BB66-D184F0C25556' ,@notify_level_email = 2, @notify_email_operator_name = 'SQLalerts'
EXEC msdb.dbo.sp_update_job @job_ID = '7EA95731-1E19-40F6-A5E3-325647DACDE9' ,@notify_level_email = 2, @notify_email_operator_name = 'SQLalerts'
```

![notify level](/assets/images/2022-03-03-13-46-46.png)
