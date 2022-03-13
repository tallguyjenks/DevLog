---
id: y6hc54p919aj728ggkjtzgg
title: Cleaner Code in the Where Clause
desc: ''
updated: 1647035596236
created: 1647035486778
---

In your code start your WHERE clause with a `WHERE TRUE` so that all logical statements are in `AND` statement on subsequent lines and therefore more easily commented out.

```sql
SELECT *
FROM dbo.my_table
WHERE TRUE
AND person_id > 5
AND age BETWEEN 18 AND 65
AND first_name LIKE '%Paul%'
```
