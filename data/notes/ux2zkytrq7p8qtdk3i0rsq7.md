

- `Author:` Ahmed Besbes
- `Link:` <https://towardsdatascience.com/why-you-should-start-using-pathlib-as-an-alternative-to-the-os-module-d9eccd994745>
- `Publish Date:` 2021.12.16
- `Reviewed Date:` [[import.research.article.2021.12.16]] 

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

- Negates the need to combine [[s.l.python.libs.os]] with [[s.l.python.libs.glob]] to find paths that match a given pattern.
- [[s.l.python.libs.os]] represents paths at their most simple level: strings whereas pathlib represents them as a class 

## Get common paths in a command

```python
from pathlib import Path

cwd = Path.cwd()
home = Path.home()
```

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

- `.exists()` : To check if the path really exists on the filesystem
- `.is_dir()` : To check if the path corresponds to a directory
- `.is_file()` : To check if the path corresponds to a file
- `.is_absolute()` : To check if the path is absolute
- `.chmod()` : To change the file mode and permissions
- `.is_mount()` : To check if the path is a mount point
- `.suffix` : Get the extension of a file

