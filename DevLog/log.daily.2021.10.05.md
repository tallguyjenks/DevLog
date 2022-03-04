---
id: qku0idflysp23qys9amkc3w
title: '05'
desc: ''
updated: 1641455686434
created: 1641105063971
stub: false
isDir: false
---


#### Inputs

#### Notes

If a file in Python is opened without a context manager or is just taken up by a python process then to get it to let go of the file to delete it, open it in python, assign it to a variable then run the close method:

```python
f = open('file.txt')
f.close()
```

