

### Modular Arithmatic

```r
transmute(flights,
  dep_time,
  hour = dep_time %/% 100, #------------------------# %/% is integer division
  minute = dep_time %% 100 #------------------------# %% is remainder division
)
```
