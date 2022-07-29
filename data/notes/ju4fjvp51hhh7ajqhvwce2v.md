

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
