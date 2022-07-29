

## Sample Implementation

> from: <https://stackoverflow.com/a/50255847/12339658>

```python
from typing import Protocol

class SupportsClose(Protocol):
    def close(self) -> None:
        # ...

class Resource:
    # ...
    def close(self) -> None:
        self.file.close()
        self.lock.release()

def close_all(things: Iterable[SupportsClose]) -> None:
    for thing in things:
        thing.close()

file = open('foo.txt')
resource = Resource()
close_all([file, resource])  # OK!
close_all([1])     # Error: 'int' has no 'close' method
```

---

- Related:
  - [[s.l.python.libs.typing]]
  - [[s.l.python.oop.abstract-base-classes]]

