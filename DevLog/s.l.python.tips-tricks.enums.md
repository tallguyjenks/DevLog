---
id: ju4fjvp51hhh7ajqhvwce2v
title: Enums
desc: ''
updated: 1641522216087
created: 1641423091668
---


## enums with the [[s.l.python.libs.enum]] module

```python
from enum import Enum
Season = Enum('Season', 'winter summer spring autumn')
print(Season.summer.name)
print(Season.summer.value)

#using class
class Season(Enum):
winter = 1
summer = 2
spring = 3
autumn = 4
print(Season.winter.name)
print(Season.winter.value)

# Output:
# summer
# 2
# winter
# 1
```
