---
collapsed:: : false
title: loguru
tags: library
---

- [GitHub](https://github.com/Delgan/loguru)
- import and send a log message straight to terminal
	-
	  ```python
	  from loguru import logger
	  
	  logger.debug("That's it, beautiful and simple logging!")
	  
	  ```
- want to add a log file as well as sending to stdout? simply pass the path to the file and it will append or create if it doesnt exist
	-
	  ```python
	  logger.add("app.log")
	  ```
	- you can also use variable components:
		-
		  ```python
		  
		  ```
		-