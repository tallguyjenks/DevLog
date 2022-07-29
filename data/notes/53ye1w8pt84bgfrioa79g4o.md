

Unlike aggregate functions such as `MIN` or `MAX` using `LEAST` or `GREATEST` seems to be scalar oriented

> Two functions that come in handy for data preparation are the `LEAST` and `GREATEST` functions. Each function takes any number of values and returns the least or the greatest of the values, respectively.
>
> A simple use of this variable would be to replace the value if it's too high or low. For example, the sales team may want to create a sales list where every scooter is $600 or less than that. We can create this using the following query:

```sql
SELECT product_id
     , model
     , year
     , product_type
     , LEAST(600.00, base_msrp) AS base_msrp
     , production_start_date
     , production_end_date
FROM products
WHERE product_type='scooter'
ORDER BY 1;
```


