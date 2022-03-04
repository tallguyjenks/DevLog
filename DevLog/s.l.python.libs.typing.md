---
id: pu6oqj5pld9iybahio08rqt
title: Typing
desc: ''
updated: 1641427044064
created: 1641105063870
stub: false
isDir: false
---


- To do a type annotation for items in a list (a vector basically) you can pass the type like `list[int]` but this can also be used to pass things like a list of int lists: `list[list[int]]`
- But now in newer versions of python you can just use the built in types
  - To use `List` as a type you need to `from typing import List` : `List[List[int]]`
  - Dictionary typing: `x: Dict[str, str] = {"a": "b"}`
    - `from typing import Dict`
  - Set typing: `x: Set[str] = {"a", "b"}`
    - `from typing import Set`
  - Now all of these are available as `set` `dict` `list`

---

- Reference:
  - [[r.+.2021.12.15.python-typing-type-hints-and-annotations]]
- Related:
  - [[s.l.python.oop.protocol-classes]]

