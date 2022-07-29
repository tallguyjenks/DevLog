

> “Software entities … should be open for extension but closed for modification”

In other words: You should not need to modify the code you have already written to accommodate new functionality, but simply add what you now need.

Intention: Add a `Median` function

```python
import numpy as np
from abc import ABC, abstractmethod

class Operations(ABC):
    '''Operations'''
    @abstractmethod
    def operation():
        pass

class Mean(Operations):
    '''Compute Max'''
    def operation(list_):
        print(f"The mean is {np.mean(list_)}") 

class Max(Operations):
    '''Compute Max'''
    def operation(list_):
        print(f"The max is {np.max(list_)}") 

class Main:
    '''Main'''
    @abstractmethod
    def get_operations(list_):
        # __subclasses__ will found all classes inheriting from Operations
        for operation in Operations.__subclasses__():
            operation.operation(list_)


if __name__ == "__main__":
    Main.get_operations([1,2,3,4,5])
# The mean is 3.0
# The max is 5
```

---

- Reference:
  - [[SOLID Coding in Python|r.(.2021.11.10.solid-coding-in-python]]
- Related:
  - [[Python Abstract Base Classes|s.l.python.oop.abstract-base-classes]]

