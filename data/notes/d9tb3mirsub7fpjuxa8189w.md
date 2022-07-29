

### Transmute

```r
transmute(flights_small, #----------------------------------# Using transmute will let you mutate the variables but keeps only 
gain = arr_delay - dep_delay,                        # The Newly mutated variables in your tibble
speed = distance / air_time * 60, 
hours = air_time / 60,
gain_per_hour = gain / hours 
)
```
