---
id: p7a2j2fpvrlc9qxq0w2b08i
title: Extract Date Parts
desc: ''
updated: 1643228701713
created: 1643228489417
---


```sql
SELECT current_date
     , EXTRACT(dow FROM current_date) AS day_of_week
     , EXTRACT(week FROM current_date) AS week_of_year
     , EXTRACT(quarter FROM current_date) AS quarter;

/*

current_date | day_of_week | week | quarter
-------------+-------------+------+--------
2019-04-28   |           0 |   17 |       2
(1 row)

*/
```


