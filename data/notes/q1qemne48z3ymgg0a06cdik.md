
Instead of eplicitly adding each separator

```sql
SELECT CONCAT(first_name, ' ', last_name) FROM person_table;
```

> `CONCAT_WS(<separator>, <data>)`

```sql
SELECT CONCAT_WS(' ', first_name, middle_name, last_name) FROM person_table;
```
