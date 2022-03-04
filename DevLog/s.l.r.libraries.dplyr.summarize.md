---
id: njrwd2djl9r5gyomawxsuwc
title: Summarize
desc: ''
updated: 1641410073914
created: 1641410073915
---


### Summarize

```r
avgDelay <- as.numeric(summarize(flights, delay = mean(dep_delay, na.rm = T)))
cat("The average delay of all flights is:", avgDelay)

by_day <- group_by(flights, year, month, day)
summarize(by_day, delay = mean(dep_delay,na.rm = T))
```
