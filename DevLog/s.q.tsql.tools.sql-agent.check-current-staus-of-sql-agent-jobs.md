---
id: 18xdjwcms900gvn1tqfntl4
title: Check Current Staus of Sql Agent Jobs
desc: ''
updated: 1646343548286
created: 1646343474388
---

```sql
SELECT job_id, name, enabled FROM msdb.dbo.sysjobs

-- or this version

SELECT SJ.job_id
     , SJ.name
     , SJ.enabled
     , SC.name AS category
FROM msdb.dbo.sysjobs AS SJ
INNER JOIN msdb.dbo.syscategories AS SC
    ON SJ.category_id = SC.category_id
```
