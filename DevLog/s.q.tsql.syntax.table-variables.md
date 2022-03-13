---
id: 7hanwbehk5bvvqeb2ouiptu
title: Table Variables
desc: ''
updated: 1646340431310
created: 1646340352150
---

```sql
-- Table variable
DECLARE @tablevariable TABLE (customerid [int] NOT NULL PRIMARY KEY, lastorderdate [datetime] NULL);

INSERT INTO @tablevariable
SELECT customerid, max(orderdate) AS lastorderdate
FROM sales.SalesOrderHeader
GROUP BY customerid;

SELECT *
FROM sales.salesorderheader AS soh
INNER JOIN @tablevariable AS t
    ON soh.customerid = t.customerid
        AND soh.orderdate = t.lastorderdate
GO
```
