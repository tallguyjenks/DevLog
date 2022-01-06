---
id: gN7QNEOT7vhigGDpN62ii
title: Generics
desc: ''
updated: 1641426985085
created: 1641426985085
---

### Generics:

```python
from typing import TypeVar, List

T = TypeVar('T')

def get_item(lst: List[T], index: int) -> T:
	return lst[index]
```
