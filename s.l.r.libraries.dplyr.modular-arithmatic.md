---
id: EfBoCegEK0IPpRs7LPO8z
title: Modular Arithmatic
desc: ''
updated: 1641410064570
created: 1641410064570
---

### Modular Arithmatic

```r
transmute(flights,
  dep_time,
  hour = dep_time %/% 100, #------------------------# %/% is integer division
  minute = dep_time %% 100 #------------------------# %% is remainder division
)
```
