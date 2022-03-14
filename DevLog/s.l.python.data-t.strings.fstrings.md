---
id: ceszwn6ix85el7c951slbag
title: Fstrings
desc: ''
updated: 1647279564722
created: 1641421049730
---


- [Python 3's f-Strings: An Improved String Formatting Syntax (Guide)](https://realpython.com/python-f-strings/)
- F String format specifications







---

### Formatting

---

- format fstrings with a colon in the brace and the format on the right hand side

`import datetime; print(f'{datetime.datetime.utcnow():%Y-%m-%d}')`

---

### Nested Formatting

---

```python
num_value = 123.456
nested_format = ".2f"
print(f'{num_value:{nested_format}}')
# >>> 123.46
```
