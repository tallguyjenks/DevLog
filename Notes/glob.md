---
tags: 💻️/Python/Library
publish: true
aliases:
  - 
cssclass: 
created: 2022-01-07 1741
updated: 2022-01-07 1742
---

# [[glob]]

---

> glob contains the [[os]], [[sys]], and [[re]] modules.

```python
import glob
glob.glob('/home/user', '*')
```

  | Wildcard | Matches                                       | Example                                               |
  |----------|-----------------------------------------------|-------------------------------------------------------|
  | *        | any characters                                | \*.txt matches all files with the txt extension        |
  | ?        | any one character                             | ??? matches files with 3 characters long              |
  | []       | any character listed in the brackets          | [ABC]* matches files starting with A,B or C           |
  | [..]     | any character in the range listed in brackets | [A..Z]* matches files starting with capital letters   |
  | [!]      | any character listed in the brackets          | [!ABC]* matches files that do not start with A,B or C |

---

- Tags: 
	- 
- Reference:
	- 
- Related:
	- 
