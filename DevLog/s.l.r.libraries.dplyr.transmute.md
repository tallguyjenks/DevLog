---
id: nzy3340nn4yw6r8z66f8muw
title: Transmute
desc: ''
updated: 1641410056314
created: 1641410056314
---


### Transmute

```r
transmute(flights_small, #----------------------------------# Using transmute will let you mutate the variables but keeps only 
gain = arr_delay - dep_delay,                        # The Newly mutated variables in your tibble
speed = distance / air_time * 60, 
hours = air_time / 60,
gain_per_hour = gain / hours 
)
```
