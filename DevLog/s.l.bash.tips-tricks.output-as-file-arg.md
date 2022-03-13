---
id: byak2mlhlsr2u6fzj4irbn0
title: Output as File Arg
desc: ''
updated: 1641429260125
created: 1641429260125
---


### Use the output of another command as a file argument

```bash
wc file1 <(echo “hello world”) file2
```

> When you wrap a command with `<(...)` bash generate a temporal file in a path like `/dev/fd/64`, then execute your wrapped command, put the output in this temporal file, and finally replace `<(...)` with the filename of the temporal file, in this case, `/dev/fd/64`
