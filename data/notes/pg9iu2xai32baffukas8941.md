

### Arrange

```r
arrange(flights, desc(is.na(dep_time))) #-------------------# Sorted on the dep_time column using is.na to put missing values at top
arrange(flights, desc(dep_delay)) #-------------------------# most delayed flights
arrange(flights, dep_delay) #-------------------------------# flights that left the earliest, AESC is the default setting so no function exists for that
arrange(flights, air_time) #--------------------------------# Fastest flights
arrange(flights, desc(distance), desc(air_time)) #----------# flights that traveled the longest
arrange(flights, distance) #--------------------------------# flights that traveled the shortest
```
