
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
