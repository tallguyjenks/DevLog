---
id: JqbJjGiUDRk67kDLWo7Ri
title: Indexes
desc: ''
updated: 1643273498620
created: 1643273488614
---

```sql
CREATE UNIQUE INDEX "CIX_Year_Loc"
    ON rpt.location_trended USING btree
    ("Year" ASC NULLS LAST, "Location" COLLATE pg_catalog."default" ASC NULLS LAST)
    INCLUDE ("Year", "Location")
    TABLESPACE pg_default;
    ALTER TABLE rpt.location_trended CLUSTER ON "CIX_Year_Loc";
```


