---
id: 9gzl2f4a4qkshd4haffpemu
title: Writeable Cte
desc: ''
updated: 1643222465333
created: 1643222381450
---


![writeable CTE](/assets/images/2022-01-26-10-39-53.png)

```sql
-- Delete rows while simultaneously
-- inserting them elsewhere
WITH moved_rows AS (
    DELETE FROM products
    WHERE date >= '2010-10-01' AND date < '2010-11-01'
    RETURNING *
)
INSERT INTO products_log SELECT * FROM moved_rows;
```


