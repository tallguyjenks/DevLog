

### Tuple Type:

```python
from typing import Tuple

# This is an error because the tuple can contain items of differing types 
# so you need to specify the type of each item within it
x: Tuple[int] = (1, 2, 3) 

x: Tuple[int, int, int] = (1, 2, 3)
```
