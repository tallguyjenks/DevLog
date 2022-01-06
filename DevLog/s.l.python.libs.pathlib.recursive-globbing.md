---
id: xNXwg0qyRw804tvpIfnDx
title: Recursive Globbing
desc: ''
updated: 1641426346815
created: 1641426346815
---

## Recursive globbing

```python

from pathlib import Path

# A quite large folder indeed!
path = Path("/Users/ahmed.besbes/anaconda3/")

python_files = path.rglob("**/*.py")

next(python_files)
# PosixPath('/Users/ahmed.besbes/anaconda3/bin/rst2xetex.py')

next(python_files)
# PosixPath('/Users/ahmed.besbes/anaconda3/bin/rst2latex.py')

next(python_files)
# PosixPath('/Users/ahmed.besbes/anaconda3/bin/rst2odt_prepstyles.py')

...

len(list(python_files))
# 67481
```
