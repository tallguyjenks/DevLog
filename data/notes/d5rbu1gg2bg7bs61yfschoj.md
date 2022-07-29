

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
