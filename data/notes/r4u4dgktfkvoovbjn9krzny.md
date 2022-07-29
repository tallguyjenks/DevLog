

```r
knitr::opts_chunk$set(echo = TRUE, results = 'hide')
library(tidyverse)
library(nycflights13)
```

## Initial Items

```r
nycflights13::flights

airlines #--------------------------------------------------# not just a data frame but a tibble
view(flights) #---------------------------------------------# opens the viewer on the tibble so we can observe data in tabular format
filter(flights, month == 1, day == 1) #---------------------# prints the result of the filter
jan1 <- filter(flights, month == 1, day == 1) #-------------# assigns the result of the filter to a dataframe
(dec25 <- filter(flights, month == 12, day == 25)) #--------# wrapped parenthese both assigns and prints out the dataframe
sqrt(2) ^ 2 == 2 #------------------------------------------# False as its approximate and not exact, use near() to get around this
1/49 * 49 == 1 #--------------------------------------------# also false
near(sqrt(2) ^ 2,2) #---------------------------------------# Returns True as it should
near(1/49 * 49,1) #-----------------------------------------# Returns True as it should
nov_dec <- filter(flights, month %in% c(11, 12)) #----------# will select rows where x is one of the values in y
```

### More Exercises

```r
# Exercise 1
transmute(flights,
  dep_time,
  dep_hours = dep_time %/% 100,
  dep_minutes = dep_time %% 100,
  sched_dep_time,
  sched_dep_hours = sched_dep_time %/% 100,
  sched_dep_minutes = sched_dep_time %% 100
)

# Exercise 2
newFlights <- transmute(flights,
  air_time,
  realTime = arr_time - dep_time,
  accuracy = air_time == realTime
)
accurateFlights <- filter(newFlights, accuracy == T) #------# 0.36% Accuracy of AirTime

# Exercise 3
flightsDelay <- transmute(flights,
  dep_delay,
  realDelay = dep_time - sched_dep_time,
  accurate = dep_delay == realDelay
)
accurateDelays <- filter(flightsDelay, accurate == T) #-----# 67.9% Accuracy of delay times

# Exercise 4
min_rank(flightsDelay$realDelay)
subset <- sort(flightsDelay$realDelay,decreasing = T)
subset[1:10] %>% mean()

# Exercise 5
subset[1:3]+subset[1:10]
```
