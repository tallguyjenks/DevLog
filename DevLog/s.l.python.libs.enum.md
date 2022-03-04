---
id: 4r303qp34mp65k20m3ysz6b
title: Enum
desc: ''
updated: 1641416840196
created: 1641105063850
stub: false
isDir: false
---


```python
from enum import Enum

class Shake(Enum):
    VANILLA = 7
    CHOCOLATE = 4
    COOKIES = 9
    MINT = 3

for shake in Shake:
    print(shake)
	
#>>> Shake.VANILLA
#>>> Shake.CHOCOLATE
#>>> Shake.COOKIES
#>>> Shake.MINT
```
