---
id: 65rmfa6tjlcdtb6pv3vu3hp
title: The Best Way to Request User Input in Python
desc: ''
updated: 1641801161060
created: 1641800904311
---


## Installation

```bash
pip install pyinputplus
```

## Usage

```python
import pyinputplus as pyinput

prompt = 'How old are you:'
age = pyinput.inputInt(prompt=prompt, greaterThan=0)
```

## Example Output

```markdown
How old are you:-1
Number must be greater than 0.
How old are you: 11.5
'11.5' is not an integer.
How old are you: 14
```
