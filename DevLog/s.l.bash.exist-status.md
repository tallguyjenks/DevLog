---
id: 92sr3vg1lco4uvff8uaajer
title: Exist Status
desc: ''
updated: 1641428975929
created: 1641428975929
---


### Exit Status In Bash

- You can check the exit status with the exit status variable:

```shell
echo "My script's exit status is '$?'"
```

- `$?` is only required if you need to retrieve the exact status of the previous command. If you only need to test for success or failure (any non-zero status), just test the command directly. e.g.:

```shell
if cmd; then
...
fi
```

#### Documentation

- <https://mywiki.wooledge.org/BashPitfalls>
