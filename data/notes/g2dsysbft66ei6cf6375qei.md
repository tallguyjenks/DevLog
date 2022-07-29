

## Easy file manipulation

```python
from pathlib import Path

random_file = Path("random_file.txt")

random_file.exists()
# False

random_file.touch()

random_file.exists()
# True
```
