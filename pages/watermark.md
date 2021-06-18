---
collapsed:: false
title: watermark
tags: library
---

- used in [[Jupyter]] to grab system and package info:
	- In a jupyter cell:
		-
		  ```python
		  pip install watermark
		  %load_ext watermark
		  %watermark?
		  %watermark --machine --python --packages black,flake8,isort
		  ```
		-