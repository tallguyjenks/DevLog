---
id: zfViZf0NN958Wkv9WZAqi
title: Redirections
desc: ''
updated: 1641428968373
created: 1641428968373
---

### Bash Redirections

When Bash starts, normally, 3 file descriptors are opened, 0, 1 and 2 also known as standard input (`stdin`), standard output (`stdout`) and standard error (`stderr`).

| num | val      |
| --- | -------- |
| 0   | `stdin`  |
| 1   | `stdout` |
| 2   | `stderr` |

```shell
2>/dev/null
```

#### Documentation

- <https://wiki.bash-hackers.org/howto/redirection_tutorial>
