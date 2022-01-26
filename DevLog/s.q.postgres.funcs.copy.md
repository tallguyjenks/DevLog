---
id: 8fTMyVD9AmijpTELfbCsO
title: Copy
desc: ''
updated: 1643227674365
created: 1643227649367
---

> The COPY statement retrieves data from your database and dumps it in the file format of your choosing. For example, take the following statement:

```sql
COPY (SELECT * FROM customers LIMIT 5) TO STDOUT WITH CSV HEADER;
```


