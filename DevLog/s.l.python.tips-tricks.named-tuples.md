---
id: d5rbu1gg2bg7bs61yfschoj
title: Named Tuples
desc: ''
updated: 1641423068841
created: 1641423068841
---


## Named Tuples

```python
from collections import namedtuple

Coordinate = namedtuple("Coordinate", "longitude latitude")
location = Coordinate(90, 37.5)
print("location:", location) 
# accessing attributes with dot notation
print(location.longitude, location.latitude) 
# Output: 
# location: Coordinate(longitude=90, latitude=37.5) 
# (90, 37.5) 
```
