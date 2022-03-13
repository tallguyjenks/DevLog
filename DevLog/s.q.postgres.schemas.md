---
id: 8okmgr4axybwy9cyzjp0sq8
title: Schemas
desc: ''
updated: 1643273453501
created: 1643273424751
---



```sql
CREATE SCHEMA rpt AUTHORIZATION postgres;
COMMENT ON SCHEMA rpt IS 'Reporting';
GRANT ALL PRIVILEGES ON SCHEMA rpt TO postgres;
ALTER USER postgres SET search_path TO rpt, public;
```
