---
id: hn5kg613tevodikhy8xfsvc
title: Nesting
desc: ''
updated: 1641422561557
created: 1641422561557
---


## Functions Can Be Nested

```python
def func1(a, b): 
	def inner_func(x):
		return x*x*x 
	return inner_func(a) + inner_func(b)
```
