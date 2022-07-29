

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



