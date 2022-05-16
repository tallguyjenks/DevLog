---
id: d2533pz9tslw9nd56f5t6lo
title: Changelog
desc: ''
updated: 1652679131247
created: 1652559086416
---

## 2022-05-14

- mailer service
  - Setup DB mail profile for the mailer service
  - made the table and objects
  - Created the SQL agent job
- Create METRICS database and a heartbeat dashboard
- Add SSIS metrics tables to METRICS database under schema `ssis`
- spin up new VM to run Visual Studio
  - Install SQL Server Data Tools

## 2022-04-25

- Install SSMS (T-SQL)
  - Management > Database Mail > Configure and setup `(See [[s.q.tsql.system-resources.stored-procedure.msdb.sp_send_dbmail]])`
  - Setup alternate login

```sql
CREATE LOGIN [Bryan] WITH PASSWORD = <++>, 
DEFAULT_DATABASE=[master], 
DEFAULT_LANGUAGE=[us_english], 
CHECK_EXPIRATION=OFF, 
CHECK_POLICY=ON;
GO
ALTER SERVER ROLE [sysadmin] ADD MEMBER [Bryan];
GO
```
