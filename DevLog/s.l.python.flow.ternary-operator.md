---
id: x8jn2htcxpsj58bxl2mq1bp
title: Ternary Operator
desc: ''
updated: 1641422457261
created: 1641422457261
---


## Ternary Operator

```python
#You'll typically see:
reputation = 30
if reputation > 25:
	name = "admin"
else:
	name = "visitor"
	print(name)

reputation = 20
name = "admin" if reputation > 25 else "visitor"
print(name)
#>>> admin
#>>> visitor
```
