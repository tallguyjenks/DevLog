---
id: 5ecv2p48blb7hf03bprirsf
title: Casting
desc: ''
updated: 1643226968743
created: 1643226735015
---


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
