---
id: lcSLnBu6QTaeijL79CA7k
title: Cache
desc: ''
updated: 1641426089369
created: 1641426069688
---

## Cache

- <https://youtu.be/DnKxKFXB4NQ>
  - [[r.(.python-functools-lru_cache]]

```python
import timeit
from functools import cache
import sys
sys.setrecursionlimit(5000)
@cache
def factorial(n):
    return n * factorial(n-1) if n else 1

if __name__ == '__main__':
    print(timeit.timeit("factorial(100)", setup="from __main__ import factorial"))
```
