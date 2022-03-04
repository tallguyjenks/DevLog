---
id: qbeilegetcgtc0a1j5p1gpj
title: Parenthesized Context Managers
desc: ''
updated: 1641423485096
created: 1641423485096
---


### Parenthesized Context Managers

```python
with (open('file1.txt', 'r') as fin, open('file2.txt', 'w') as fout):
	fout.write(fin.read()) 
# In essence: cat file1.txt > file2.txt 
# if file2 were in append mode 'a' then it would be like: 
# cat file1.txt >> file2.txt
```
