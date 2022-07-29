

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


