---
id: ojg9gogpf3fx6v80nba4bj7
title: Custom
desc: ''
updated: 1641427034911
created: 1641427034911
---


### Custom Typing:

```python
from typing import List

Vector = List[float]	

def foo(v: Vector) -> Vector:
	print(v)
```

![alt](assets/images/Pasted_image_20211215085306.png)

Can also use our own custom types like this: 

```python
from typing import List

Vector = List[float]
Vectors = List[Vector]

def foo(v: Vectors) -> Vectors:
	print(v)
```
