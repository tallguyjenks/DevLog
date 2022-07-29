
```python
import os

# get file stats
stats = os.stat('f:/file.txt')
print('Size of file is', stats.st_size, 'bytes')
```
