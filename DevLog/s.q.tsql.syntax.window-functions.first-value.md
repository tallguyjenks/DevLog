---
id: ujy0563tlnn7c0zsqu67fiv
title: First Value
desc: ''
updated: 1647036591542
created: 1647036489207
---

From

```sql
WITH
orders AS (
    SELECT 
        name, 
        model,
        year, 
        date_at_lot
        row_number() over(partition by model, year order by date_at_lot asc) AS order
    FROM cars 
)
SELECT
    name AS oldest_car_name,
    model, 
    year
FROM orders
where order = 1 
```

To

```sql
SELECT 
    FIRST_VALUE(name) OVER(PARTITION BY model, year ORDER BY date_at_lot ASC) AS oldest_car_name
    model,
    year
FROM cars
```
