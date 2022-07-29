

- used in [[jupyter|s.l.python.tools.jupyter]] to grab system and package info:
  - In a jupyter cell:

```python
pip install watermark
%load_ext watermark
%watermark?
%watermark --machine --python --packages black,flake8,isort
```
