---
id: fva75vscrfhi5k6k6mfow7w
title: Stat
desc: Get the size of a file in bytes
updated: 1642545500622
created: 1642545377247
---

```python
import os

# get file stats
stats = os.stat('f:/file.txt')
print('Size of file is', stats.st_size, 'bytes')
```
