---
id: 90im3jtfbdg9hiwxwyvhz5b
title: Sequence
desc: ''
updated: 1641423244135
created: 1641423244135
---


## Sequence Type

```python
from typing import Sequence

def foo(seq: Sequence[str]):
pass
foo("Hello") # This is fine because a string is a sequence of characters
foo(("a", "b", "c")) # a Tuple is an ordered and immutable indexed Object
foo(["a", "b", "c"]) # A list is an ordered and indexed object 
foo({1, 2, 3}) # A set is hashed and not indexed or ordered so it cannot be a sequence
foo(1)
#>>> Last one throws an error because static analysis determines that it is an incompabile type
```
