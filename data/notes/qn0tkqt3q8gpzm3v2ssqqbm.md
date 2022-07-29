

```sql
EXPLAIN(FORMAT JSON)
SELECT * 
FROM public.test
WHERE hello IN (SELECT hello FROM public.test ORDER BY hello DESC LIMIT 1);
```

![query plan](/assets/images/2022-01-26-10-01-27.png)

Using `EXPLAIN(ANALYZE)` and then pasting the output of the plan into this tool gives like a flame graph:

<https://explain.depesz.com/>

![flame graph](/assets/images/2022-01-26-10-09-32.png)

This tool is also amazing for displaying graphics on a plan

<https://explain.dalibo.com/>

![query plan](/assets/images/2022-01-26-10-30-43.png)

Setting EXPLAIN to be done automatically (must be a super user to load the module)

```sql
LOAD 'auto_explain';
```

`Explain` will just provide the plan calculations

Running `Analyze` as well will actually execute the statement so if running on a `DELETE` statement be careful if just testing
