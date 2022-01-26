---
id: vgqx9gemgZrXscMqJodtF
title: Array
desc: ''
updated: 1643228930565
created: 1643228876396
---

```sql
SELECT ARRAY['Lemon', 'Bat Limited Edition' ] AS example_purchased_products;

/*

example_purchased_products
------------------------------
{Lemon, "Bat Limited Edition"}

*/
```

```sql
SELECT UNNEST(ARRAY[123, 456, 789]) AS example_ids;
```


