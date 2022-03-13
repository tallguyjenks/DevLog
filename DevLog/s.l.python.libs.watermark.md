---
id: 3ubt9a8mrwje3xnv7wf4k7n
title: Watermark
desc: ''
updated: 1641267277142
created: 1641105063872
stub: false
isDir: false
---


- used in [[jupyter|s.l.python.tools.jupyter]] to grab system and package info:
  - In a jupyter cell:

```python
pip install watermark
%load_ext watermark
%watermark?
%watermark --machine --python --packages black,flake8,isort
```
