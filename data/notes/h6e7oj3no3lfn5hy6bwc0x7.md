

### Callable Type:

```python
from typing import callable, Optional

def foo(func: Callable[[int, int, Optional[int]], int]) -> None:
	func(1, 2)

def add(x: int, y: int) -> int:
	return x + y

foo(add)

#=================================================================#

def foo() -> Callable[[int, int, Optional[int]], int]):
	def add(x: int, y: int) -> int:
		return x + y
	return add

foo()

#=================================================================#

def foo() -> Callable[[int, int], int]):
	func: Callable[[int, int], int]) = Lambda x, y: x + y
	return func

foo()
```
