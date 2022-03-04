---
id: 7fo4mvts7wx8qbcmzpcdqx1
title: Distinct
desc: ''
updated: 1641413089299
created: 1641105063934
stub: false
isDir: false
---


```sql
SELECT DISTINCT <COLUMN>
FROM <TABLE>
```

Selects only unique values from that table. 

If there are multiple columns then its every unique pairing of all values in those 2 columns that occur and the same goes on for every additional column:

```sql
SELECT DISTINCT <COLUMN 1>, [COLUMN 2], [...]
FROM <TABLE>
```
