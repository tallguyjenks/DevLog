---
id: q1qemne48z3ymgg0a06cdik
title: Concat_ws
desc: ''
updated: 1651075664407
created: 1651075554432
---

Instead of eplicitly adding each separator

```sql
SELECT CONCAT(first_name, ' ', last_name) FROM person_table;
```

> `CONCAT_WS(<separator>, <data>)`

```sql
SELECT CONCAT_WS(' ', first_name, middle_name, last_name) FROM person_table;
```

