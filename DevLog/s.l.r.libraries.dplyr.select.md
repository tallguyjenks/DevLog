---
id: ro21urp95zz9s190t6at148
title: Select
desc: ''
updated: 1641410045006
created: 1641410045006
---


### Select

```r
select(flights, year, month, day) #-------------------------# Selecting specific variables from the data set (variables = columns)
select(flights, year:day) #---------------------------------# Selecting specific variables using colon (this to this)
select(flights, -(year:day)) #------------------------------# selects all variables EXCEPT those in the parens with the minus sign operating on it
# functions to use with select
# starts_with
# ends_with
# contains
# matches
# num_range
select(flights, origin, dest, everything()) #---------------# Puts selected columns at front of data set while keeping all variable in data set
select(flights, tailnum, tailnum) #-------------------------# If same variable named twice, it is displayed only once
vars <- c("year","month","day","dep_delay","arr_delay") #---# Give character vector the variable names
select(flights,one_of(vars)) #------------------------------# Use one_of function with character vector variable to grab variables from tibble that match
select(flights, contains("TIME")) #-------------------------# Selects all tibble variables that contain substring "Time"

flights_small <- select(flights, #--------------------------# Selecting desired variables for a lean-er data set through various methods
			   year:day,
			   ends_with("delay"),
			   distance,
			   air_time
			   )
```
