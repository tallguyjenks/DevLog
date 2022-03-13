---
id: wcvo22ngydmqw72cldysy2l
title: Example
desc: ''
updated: 1641426367675
created: 1641426367675
---


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
