---
id: 9gd8rdulgt62nxapo3i84ti
title: Time
desc: ''
updated: 1641376884185
created: 1641105063894
stub: false
isDir: false
---


## C Time Library

[\\&lt;ctime>](http://cplusplus.com/reference/ctime/)

## Time Manipulation

### time

[time()](http://cplusplus.com/reference/ctime/time/)

> The value returned generally represents the number of seconds since 00:00 hours, Jan 1, 1970 UTC (i.e., the current unix timestamp). Although libraries may use a different representation of time: Portable programs should not use the value returned by this function directly, but always rely on calls to other elements of the standard library to translate them to portable types (such as `localtime`, `gmtime` or `difftime`).

```cpp
time(0)
```
