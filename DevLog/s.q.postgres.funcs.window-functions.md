---
id: 5d0n8smj0vbwy6h1kbk7gyb
title: Window Functions
desc: ''
updated: 1643227499380
created: 1643227496790
---


Examples of window functions

```sql
SELECT {columns}
     , {window_func} OVER (PARTITION BY {partition_key} ORDER BY {order_key})
FROM table1;
```

more realistic example:

```sql
SELECT customer_id
     , title
     , first_name
     , last_name
     , gender
     , COUNT(*) OVER (PARTITION BY gender ORDER BY customer_id) AS total_customers
     , SUM(CASE WHEN title IS NOT NULL THEN 1 ELSE 0 END) OVER (PARTITION BY gender ORDER BY customer_id) AS total_customers_title
FROM customers
ORDER BY customer_id;
```

The window Keyword:

```sql
SELECT customer_id
     , title
     , first_name
     , last_name
     , gender
     , COUNT(*) OVER w AS total_customers,
     , SUM(CASE WHEN title IS NOT NULL THEN 1 ELSE 0 END) OVER w AS total_customers_title
FROM customers
     WINDOW w AS (PARTITION BY gender ORDER BY customer_id) -- Reduces typing and improves legibility
ORDER BY customer_id;
```



