
## Sign

The `SIGN()` function returns a value depending on whether the column it's given is positive or negative.

- If a number is > 0, it returns 1.
- If a number is < 0, it returns -1.
- If the number is = 0, it returns 0.

This function will only work on columns that are of a number data type.

```sql
SELECT
      customer_name
    , amount
FROM bank_statements
WHERE SIGN(amount) IN (-1, 0)
```

## Lead

The `LEAD()` function saves you from needing to do a confusing, messy join to another table.
It allows you to access the values in the rows after the row you are currently looking at.
It makes comparison super easy.

In a grocery store, there are multiple different checkout lanes 1–10.
Then, within each checkout lane are different customers.
Whoever arrived first is first in line and whoever arrived last is last in line.

![customers](/assets/images/2022-03-16-13-38-16.png)

```sql
SELECT
   customer_name,
   LEAD(customer_name) OVER(PARTITION BY line_number ORDER BY arrived_at ASC) AS next_in_line
FROM grocery_customers
```

![output](/assets/images/2022-03-16-13-38-41.png)

## Lag

Opposite from the `LEAD()` function, `LAG()` allows you to compare your current row to the rows before it, rather than those after it.
It is still used for comparison, it just serves a bit of a different purpose.
Similarly, with `LEAD()`, you choose the column you wish to output from the rows before your current row and partition based on how you wish to separate out your columns.
Then, the most important part is `ORDER BY`.
This will determine whether you’re getting the value you want or not.
If you choose `ASC` or `DESC` values, that can change your whole query.
Just be sure it fits the context of your problem and what you’re trying to solve.

```sql
SELECT
   customer_name,
   LAG(Name) OVER(PARTITION BY line_number ORDER BY arrived_at ASC) AS ahead_in_line
FROM grocery_customers
```

![lag results](/assets/images/2022-03-16-13-40-28.png)

## IIF

It’s essentially a simpler `CASE` statement. The `IIF()` function tests a condition and returns a specified value if the condition is TRUE and another specified value if the condition is FALSE.

in essence it acts like the excel IF function

```sql
SELECT
  iif(1=1,'TRUE','FALSE') AS 'T'
, iif(1=0,'TRUE','FALSE') AS 'F'
```

![RESULTS](/assets/images/2022-03-16-13-46-43.png)
