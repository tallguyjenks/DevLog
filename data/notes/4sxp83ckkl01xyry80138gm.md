

unlike [[s.q.tsql]] casting doesnt require the `CAST(column AS TYPE)` function. Instead, within postgres you can cast datatypes like `column::datatype` using the double colon syntax `::`

```sql
SELECT product_id
     , model
     , year::TEXT
     , product_type
     , base_msrp
     , production_start_date
     , production_end_date
FROM products;
```
