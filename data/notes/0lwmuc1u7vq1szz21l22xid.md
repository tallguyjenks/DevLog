

- `URL:` <https://youtu.be/QORvB-_mbZ0>
- `Channel/Host:` Tech With Tim
- `Reference:` [[Typing|s.l.python.libs.typing]]
- `Publish Date:` 2021.09.29
- `Reviewed Date:` [[log.daily.2021.12.15]]

---

<center><iframe width="560" height="315" src="https://www.youtube.com/embed/QORvB-_mbZ0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></center>

---

- [09:20](https://youtu.be/QORvB-_mbZ0#t=560.036194) 
  - To do a type annotation for items in a list (a vector basically) you can pass the type like `list[int]` but this can also be used to pass things like a list of int lists: `list[list[int]]`
  - To use `List` as a type you need to `from typing import List` : `List[List[int]]`
- [10:31](https://youtu.be/QORvB-_mbZ0#t=631.544946)
  - `from typing import Dict`
  - Dictionary typing: `x: Dict[str, str] = {"a": "b"}`
- [10:56](https://youtu.be/QORvB-_mbZ0#t=656.309631835968)
  - `from typing import Set`
  - Set typing: `x: Set[str] = {"a", "b"}`
- [11:42](https://youtu.be/QORvB-_mbZ0#t=702.2289898435974)\`
  - Custom Typing:
  - ```python
    from typing import List

    Vector = List[float]	

    def foo(v: Vector) -> Vector:
    	print(v)
    ```
  - ![alt](assets/images/Pasted_image_20211215085306.png)
  - Can also use our own custom types like this: 
  - ```python
    from typing import List

    Vector = List[float]
    Vectors = List[Vector]

    def foo(v: Vectors) -> Vectors:
    	print(v)
    ```
- [14:22](https://youtu.be/QORvB-_mbZ0#t=862.292403)
  - Optional typing
  - ```python
    from typing import Optional

    def foo(output: Optional[bool]=False):
    	pass
    foo()
    ```
- [14:33](https://youtu.be/QORvB-_mbZ0#t=873.880233)
  - Any Type is the same as not adding an annotation but more explicit
  - ```python
    from typing import Any

    def foo(output: Any):
    	pass
    ```
- [15:25](https://youtu.be/QORvB-_mbZ0#t=925.293389)
  - Sequence Type
  - ```python
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
- [17:11](https://youtu.be/QORvB-_mbZ0#t=1031.02662)
  - Tuple Type:
  - ```python
    from typing import Tuple

    # This is an error because the tuple can contain items of differing types 
    # so you need to specify the type of each item within it
    x: Tuple[int] = (1, 2, 3) 

    x: Tuple[int, int, int] = (1, 2, 3)
    ```
- [18:16](https://youtu.be/QORvB-_mbZ0#t=1096.941175)
  - Callable Type:
  - ```python
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
- [21:40](https://youtu.be/QORvB-_mbZ0#t=1300.829273)
  - Generics:
  - ```python
    from typing import TypeVar, List

    T = TypeVar('T')

    def get_item(lst: List[T], index: int) -> T:
    	return lst[index]
    ```

