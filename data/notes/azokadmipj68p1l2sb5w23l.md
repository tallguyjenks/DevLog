
- [[p.doing.homelab.services.proxmox.vm.win10-ssms]]
  - Install SSMS (T-SQL)
- [[p.doing.homelab.services.proxmox.lxe.mssql]]
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
