---
id: bA1ehIksZyQ3rBiAHWdha
title: Query Tuning with Explain
desc: ''
updated: 1643220656908
created: 1643219775679
---

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

Setting EXPLAIN to be done automatically (must be a super user to load the module)

```sql
LOAD 'auto_explain';
```

