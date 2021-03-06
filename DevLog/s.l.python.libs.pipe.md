---
id: revsl0hsui1dk3s64u80rhm
title: Pipe
desc: ''
updated: 1641202937930
created: 1641105063860
stub: false
isDir: false
---


```python
arr = [1, 2, 3, 4, 5]
list(map(lambda x: x * 2, filter(lambda x: x % 2 == 0, arr)))
# >>> [4, 8]
```

```python
from pipe import where, select
arr = [1, 2, 3, 4, 5]
list(arr,
	 | where(lambda x: x % 2 == 0, arr)
	 | select(lambda x: x * 2))
# >>> [4, 8]
```

```python
from pipe import where
arr = [1, 2, 3, 4, 5]
list(arr | where(lambda x: x % 2 == 0))
# >>> [2, 4]
```

```python
from pipe import where, select
arr = [1, 2, 3, 4, 5]
list(arr | select(lambda x: x * 2))
# >>> [2, 4, 6. 8, 10]
```

```python
from pipe import chain
nested = [[1, 2, [3]], [4, 5]]
list(nested | chain)
# >>> [1, 2, [3], 4, 5]
# OR FOR DEEPLY NESTED:
from pipe import traverse
nested = [[1, 2, [3]], [4, 5]]
list(nested | traverse)
# >>> [1, 2, 3, 4, 5]
```

```python
from pipe import traverse, select
fruits = [
	{"name": "apple", "price": [2, 5]},
	{"name": "orange", "price": 4},
	{"name": "grape", "price": 5},
]
list(fruits
	 | select(lambda fruit: fruit["price"])
	 | traverse)
```

```python
from pipe import groupby, select 
list( 
	(1, 2, 3, 4, 5, 6, 7, 8, 9)
	| groupby( lambda x: "Even" if x % 2 == 0 else "Odd") 
	| select( lambda x: {x[0]: list(x[1])})
)
# >>> [{'Even': [2, 4, 6 ,8]}, {"Odd": [1, 3, 5, 7, 9]}]
```

```python
from pipe import groupby, select 
list( 
	(1, 2, 3, 4, 5, 6, 7, 8, 9)
	| groupby( lambda x: "Even" if x % 2 == 0 else "Odd") 
	| select( lambda x: {x[0]: list(x[1] | where(lambda x: x > 2))})
)
# >>> [{'Even': [4, 6 ,8]}, {"Odd": [3, 5, 7, 9]}]
```

- Reference:
  - [[Write Clean Python Code Using Pipes|r.(.2021.11.05.write-clean-python-code-using-pipes]]
