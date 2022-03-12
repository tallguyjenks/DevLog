---
id: e9ek28fwcby9le0tz25tdbh
title: Pipe Stdout and Stderr to Separate Commands
desc: ''
updated: 1647045846433
created: 1647045799622
---

```bash
some_command > >(/bin/cmd_for_stdout) 2> >(/bin/cmd_for_stderr)
```
