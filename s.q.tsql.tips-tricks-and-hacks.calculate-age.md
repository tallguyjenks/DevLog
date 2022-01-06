---
id: VzZlo27Dn0ZiU8pRfgRFN
title: Calculate Age
desc: ''
updated: 1641412778772
created: 1641105063931
stub: false
isDir: false
---


```sql
-- The '365.25' uses .25 to account for leap year
FLOOR(DATEDIFF(DAY, <birthdate>, GETDATE())/365.25) AS Age
```
