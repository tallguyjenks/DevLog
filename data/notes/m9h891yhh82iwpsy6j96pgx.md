

> glob contains the [[os|import.os]], [[sys|import.sys]], and [[re|import.re]] modules.

```python
import glob
glob.glob('/home/user', '*')
```

| Wildcard | Matches                                       | Example                                                |
| -------- | --------------------------------------------- | ------------------------------------------------------ |
| \*       | any characters                                | \*.txt matches all files with the txt extension        |
| ?        | any one character                             | ??? matches files with 3 characters long               |
| \[]      | any character listed in the brackets          | [ABC]\* matches files starting with A,B or C           |
| [..]     | any character in the range listed in brackets | [A..Z]\* matches files starting with capital letters   |
| [!]      | any character listed in the brackets          | [!ABC]\* matches files that do not start with A,B or C |
