

```sql
CREATE TABLE rpt.report_data
(
    "payment_date" timestamp without time zone NOT NULL,
    "address" character varying (255) NOT NULL,
    "amount" numeric
);
ALTER TABLE rpt.report_data OWNER to postgres;
```
