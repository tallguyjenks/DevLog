---
id: yMRpoRlqDeY1KvE9zXpAk
title: Custom
desc: ''
updated: 1641423222440
created: 1641423222440
---

- Using the `typing` library you can import types for data structures and custom types more than just the standard primitive types

## Custom Typing

```python
from typing import List

Vector = List[float]	

def foo(v: Vector) -> Vector:
	print(v)
```

![alt](assets/images/Pasted image 20211215085306.png)

### Can also use our own custom types like this:

```python
from typing import List

Vector = List[float]
Vectors = List[Vector]

def foo(v: Vectors) -> Vectors:
	print(v)
```
