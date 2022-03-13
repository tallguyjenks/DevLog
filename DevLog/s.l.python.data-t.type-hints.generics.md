---
id: qx7q09hsjuk03qfufvg0f2d
title: Generics
desc: ''
updated: 1641423261917
created: 1641423261917
---


## Generics:

```python
from typing import TypeVar, List

T = TypeVar('T')

def get_item(lst: List[T], index: int) -> T:
	return lst[index]
```
