---
id: yajvowf7o82s94uj991cohu
title: Re Use Cmd Args
desc: ''
updated: 1641429298131
created: 1641429298131
---


### Re-use command arguments

```bash
mkdir very-large-directory-name
cd very-large-directory-name
# Instead of duplicating the argument of the mkdir command, you can use !$ for retrieve the last argument of the last command, the result is:
mkdir very-large-directory-name
cd !$ # == cd very-large-directory-name
```
