

### Filters

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
