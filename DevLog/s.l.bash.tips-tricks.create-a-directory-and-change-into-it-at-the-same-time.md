---
id: tg7ggg895gwd22vlbx6ifn8
title: Create a Directory and Change into It at the Same Time
desc: ''
updated: 1647046154628
created: 1647046147152
---

```bash
mkd() { mkdir -p "$@" && cd "$@"; }
```
