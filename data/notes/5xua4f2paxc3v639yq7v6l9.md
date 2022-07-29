

## Array data

```sql
SELECT ARRAY['Lemon', 'Bat Limited Edition' ] AS example_purchased_products;

/*

example_purchased_products
------------------------------
{Lemon, "Bat Limited Edition"}

*/
```

## Unnest array

```sql
SELECT UNNEST(ARRAY[123, 456, 789]) AS example_ids;
```

![unested array](/assets/images/2022-01-26-12-29-12.png)

This is a great way to add tags to an item in a single column in a better way than using string split on csv values!

## Array aggregate

```sql
SELECT product_type, ARRAY_AGG(DISTINCT model) AS models FROM products GROUP BY 1;
```

![array_agg](/assets/images/2022-01-26-12-31-31.png)

## String splitting to array

```sql
SELECT STRING_TO_ARRAY('hello there how are you?', ' ');
```

![string to array](/assets/images/2022-01-26-12-32-26.png)

