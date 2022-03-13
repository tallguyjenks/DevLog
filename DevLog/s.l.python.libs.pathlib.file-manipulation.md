---
id: g2dsysbft66ei6cf6375qei
title: File Manipulation
desc: ''
updated: 1641426333068
created: 1641426333068
---


## Easy file manipulation

```python
from pathlib import Path

random_file = Path("random_file.txt")

random_file.exists()
# False

random_file.touch()

random_file.exists()
# True
```
