---
id: f9k6hlerfc2a06oyy7qay93
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
