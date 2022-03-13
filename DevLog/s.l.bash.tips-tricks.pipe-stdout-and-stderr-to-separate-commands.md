---
id: yhcd8xzriuqas724an5usp5
title: Pipe Stdout and Stderr to Separate Commands
desc: ''
updated: 1647045846433
created: 1647045799622
---

```bash
some_command > >(/bin/cmd_for_stdout) 2> >(/bin/cmd_for_stderr)
```
