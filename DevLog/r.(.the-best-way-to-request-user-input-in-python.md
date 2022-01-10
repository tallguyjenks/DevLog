---
id: AyBVGeM9Y7RxLG4W04Ypt
title: The Best Way to Request User Input in Python
desc: ''
updated: 1641800992911
created: 1641800904311
---

## Installation

```bash
pip install pyinputplus
```

```python
import pyinputplus as pyinput

prompt = 'How old are you:'
age = pyinput.inputInt(prompt=prompt, greaterThan=0)
```
