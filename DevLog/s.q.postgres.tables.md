---
id: jo38zp3dzh7dh9gneg09l42
title: Tables
desc: ''
updated: 1643273474184
created: 1643273461554
---


```sql
CREATE TABLE rpt.report_data
(
    "payment_date" timestamp without time zone NOT NULL,
    "address" character varying (255) NOT NULL,
    "amount" numeric
);
ALTER TABLE rpt.report_data OWNER to postgres;
```
