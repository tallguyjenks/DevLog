---
collapsed:: false
tags: library
---

-
  ```r
  knitr::opts_chunk$set(echo = TRUE, results = 'hide')
  library(tidyverse)
  library(nycflights13)
  ```
# Initial Items
	-
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
- **Exercises**
	- DPLYR Functions
		- Filters
		  collapsed:: true
			-
			  ```r
			  filter(flights, arr_delay >= 2) #---------------------------# arrival delay greater than 2 hours
			  filter(flights, dest %in% c("IAH", "HOU")) #----------------# flew to IAH or HOU
			  filter(flights, carrier %in% c("UA","AA","DL")) #-----------# Operated by United, American, or Delta
			  filter(flights, between(month, left = 7, right = 9)) #------# Departed in summer (July, August, September)
			  filter(flights, arr_delay > 120 & dep_delay <= 0)#----------# arrived more than 2 hours late but(AND) didnt leave late
			  filter(flights, dep_delay >= 120 & arr_delay <= 90) #-------# delayed by at least an hour but made up 30min in flight
			  filter(flights, between(dep_time,left = 0, right = 600)) #--# departed between midnight and 6am (Inclusive), using between() 
			  filter(flights, is.na(dep_time))#---------------------------# count of flights with missing departure time
			  ```
		- Arrange 
		  collapsed:: true
			-
			  ```r
			  arrange(flights, desc(is.na(dep_time))) #-------------------# Sorted on the dep_time column using is.na to put missing values at top
			  arrange(flights, desc(dep_delay)) #-------------------------# most delayed flights
			  arrange(flights, dep_delay) #-------------------------------# flights that left the earliest, AESC is the default setting so no function exists for that
			  arrange(flights, air_time) #--------------------------------# Fastest flights
			  arrange(flights, desc(distance), desc(air_time)) #----------# flights that traveled the longest
			  arrange(flights, distance) #--------------------------------# flights that traveled the shortest
			  ```
		- Select
		  collapsed:: true
			-
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
		- Mutate
		  collapsed:: true
			-
			  ```r
			  mutate(flights_small, 
			       gain = arr_delay - dep_delay, #----------------------# Usage of "=" instead of <- because its assigning that value to the variable
			       speed = distance / air_time * 60, #------------------# we're saying that this variable is "=" to this equation
			       hours = air_time / 60, #-----------------------------# Not that we're assigning these valus to a vector
			       gain_per_hour = gain / hours #-----------------------# Can even use new variables made within mutate to create new variables
			       ) #--------------------------------------------------# if we had used "<-" then it displayed the operator in the variable name 
			  ```
		- Transmute
		  collapsed:: true
			-
			  ```r
			  transmute(flights_small, #----------------------------------# Using transmute will let you mutate the variables but keeps only 
			       gain = arr_delay - dep_delay,                        # The Newly mutated variables in your tibble
			       speed = distance / air_time * 60, 
			       hours = air_time / 60,
			       gain_per_hour = gain / hours 
			  )
			  ```
			  
			  <!-- Converted to RMD on 20190717 -->
			  <!-- 20190717 After This Point -->
		- Modular Arithmatic
		  collapsed:: true
			-
			  ```r
			  transmute(flights,
			          dep_time,
			          hour = dep_time %/% 100, #------------------------# %/% is integer division
			          minute = dep_time %% 100 #------------------------# %% is remainder division
			  )
			  ```
		- More Exercises
		  collapsed:: true
			-
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
		- Summarize
		  collapsed:: true
			-
			  ```r
			  avgDelay <- as.numeric(summarize(flights, delay = mean(dep_delay, na.rm = T)))
			  cat("The average delay of all flights is:", avgDelay)
			  
			  by_day <- group_by(flights, year, month, day)
			  summarize(by_day, delay = mean(dep_delay,na.rm = T))
			  ```