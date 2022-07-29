

### Summarize

```r
avgDelay <- as.numeric(summarize(flights, delay = mean(dep_delay, na.rm = T)))
cat("The average delay of all flights is:", avgDelay)

by_day <- group_by(flights, year, month, day)
summarize(by_day, delay = mean(dep_delay,na.rm = T))
```
