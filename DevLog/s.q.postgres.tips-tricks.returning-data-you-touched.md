---
id: 6xeon30b5pkgfxpwn41pg9g
title: Returning Data You Touched
desc: ''
updated: 1643221024998
created: 1643220975888
---


```sql
INSERT INTO person (name) VALUES ('Groot') RETURNING id;
/*
 id
----
  4
(1 row)
*/
```


