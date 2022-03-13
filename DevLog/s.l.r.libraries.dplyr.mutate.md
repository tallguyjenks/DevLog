---
id: mrsokqqgd9c4rjj2xcbo4pd
title: Mutate
desc: ''
updated: 1641410049032
created: 1641410049032
---


### Mutate

```r
mutate(flights_small, 
gain = arr_delay - dep_delay, #----------------------# Usage of "=" instead of <- because its assigning that value to the variable
speed = distance / air_time * 60, #------------------# we're saying that this variable is "=" to this equation
hours = air_time / 60, #-----------------------------# Not that we're assigning these valus to a vector
gain_per_hour = gain / hours #-----------------------# Can even use new variables made within mutate to create new variables
) #--------------------------------------------------# if we had used "<-" then it displayed the operator in the variable name 
```
