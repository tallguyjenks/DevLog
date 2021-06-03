---
title: PyYaml
tags: library
---

- https://pypi.org/project/PyYAML/
- https://pyyaml.org/
-
  ```python
  import yaml
  with open("example.yaml") as fp:
    data = fp.read()
  parsed = yaml.safe_load_all(data)  # parsed is a generator
  ```