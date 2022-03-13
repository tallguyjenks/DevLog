---
id: z38ie5j1080bot9snj8az5r
title: Redirect Stout and Stderr Each to Separate Files and Print Both to the Screen
desc: ''
updated: 1647045881970
created: 1647045868939
---

```bash
(some_command 2>&1 1>&3 | tee errorlog ) 3>&1 1>&2 | tee stdoutlog
```
