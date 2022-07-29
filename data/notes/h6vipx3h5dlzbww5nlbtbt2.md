
![sql-hack](/assets/images/2022-01-24-13-36-52.png)

You want to know the coolest SQL hack I learned this week?

In SQL, we often need to search character fields using the percentage (`%`) wildcard. When I put the wildcard at the end of the search string (`String%`) it uses the index, but if I put it at the front (`%String`) it does a scan of the index.

This significantly increases your run time!

```sql
-- Example:
SELECT *
FROM table
WHERE column1 LIKE 'Some_string%'

-- vs.

SELECT *
FROM table
WHERE column1 LIKE '%Some_string'
```

We say that option 1 is Sargable (Search ARGument ABLE), and option 2 is not Sargable, meaning option 2 could not leverage the index on the column.

To ensure all your wildcard queries are Sargable and to significantly decrease your run time, do the following:

```sql
SELECT *
FROM table
WHERE REVERSE(column1) LIKE REVERSE('Some_string') + '%'
```

And boom, your query runs much, much faster!
