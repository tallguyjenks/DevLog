---
id: h0j42swpcqtrn0p3slal3di
title: Sending Notification Emails with T Sql without Using Hardcoded Email Addresses
desc: ''
updated: 1646692213108
created: 1646692184363
---

```sql
USE demo

DECLARE @OperatorName sysname = N'YourOperatorName';

DECLARE @OperatorEmailAddress nvarchar(100) = (SELECT email_address FROM msdb.dbo.sysoperators WHERE [name] = @OperatorName);

PRINT @OperatorEmailAddress
```
