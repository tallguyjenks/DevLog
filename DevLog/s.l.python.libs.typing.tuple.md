---
id: uw9yjy0k615g6moimoewbr1
title: Tuple
desc: ''
updated: 1641427007910
created: 1641427007910
---


### Tuple Type:

```python
from typing import Tuple

# This is an error because the tuple can contain items of differing types 
# so you need to specify the type of each item within it
x: Tuple[int] = (1, 2, 3) 

x: Tuple[int, int, int] = (1, 2, 3)
```
