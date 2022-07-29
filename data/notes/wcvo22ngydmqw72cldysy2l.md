

```python
from pathlib import Path

path = Path('/home/johndoe/Documents/pathlib.md')
path.touch()
path.name
#>>> 'pathlib.md'
path.stem
#>>> pathlib
path.suffix
#>>> '.md'
path.parent
#>>> PosixPath('/home/johndoe/Documents')
path.parent.parent
#>>> PosixPath('/home/johndoe')
path.anchor
#>>> '/'
```
