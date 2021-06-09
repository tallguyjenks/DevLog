---
title: logging
tags: library
---

- [article on logging for a python app](https://towardsdatascience.com/the-reusable-python-logging-template-for-all-your-data-science-apps-551697c8540)
  todo:: 1620836232073
- [Official Docs](https://docs.python.org/3/library/logging.html#)
- The level of the logger:
	-
	  | Level    | Numberic Value |
	  | -        | -              |
	  | NOTSET   | 0              |
	  | DEBUG    | 10             |
	  | INFO     | 20             |
	  | WARNING  | 30             |
	  | ERROR    | 40             |
	  | CRITICAL | 50             |
-
  ```python
      import logging
      
      dir(logging)
      # items in all caps are constants
      # capitalized items are classes
      # lowercase are methods
      
      # create an configure logger
      logging.basicConfig(filename = "~/py.log")
      logger = logging.getLogger()
      
      # Test the logger
      logger.info("our first message.")
      print(logger.level) # Defaulted 30 so info and below is not shown
      ```
- From [Calm Code Rich Logging](https://calmcode.io/logging/rich.html)
	-
	  ```python
	  import logging
	  
	  from rich.logging import RichHandler
	  
	  logger = logging.getLogger(__name__)
	  
	  # the handler determines where the logs go: stdout/file
	  shell_handler = RichHandler()
	  file_handler = logging.FileHandler("debug.log")
	  
	  logger.setLevel(logging.DEBUG)
	  shell_handler.setLevel(logging.DEBUG)
	  file_handler.setLevel(logging.DEBUG)
	  
	  # the formatter determines what our logs will look like
	  fmt_shell = '%(message)s'
	  fmt_file = '%(levelname)s %(asctime)s [%(filename)s:%(funcName)s:%(lineno)d] %(message)s'
	  
	  shell_formatter = logging.Formatter(fmt_shell)
	  file_formatter = logging.Formatter(fmt_file)
	  
	  # here we hook everything together
	  shell_handler.setFormatter(shell_formatter)
	  file_handler.setFormatter(file_formatter)
	  
	  logger.addHandler(shell_handler)
	  logger.addHandler(file_handler)
	  ```
	- To have aesthetic logging output easily:
		- ![2021_06_09_image.png](https://cdn.logseq.com/%2F07ac90d5-a8a5-495c-84ae-a5c969228e38d13e2a19-7a0a-4592-aea0-166c20d3a19b2021_06_09_image.png?Expires=4776870175&Signature=N3sdSRBmibgIw6KwOZlWePVQEthzjrXjT473BDlm1SX5Biq36AdmgAb3zlsF710m0tzUr3XSaytk0e71loUxqoetAxOoKpJUlfzZ2QjrhnCZihwP-2t05tQZ4A1ybgzIUzrVKYNuM7zNHlvJTUz0WhFQTpqA8tNXuEBQFRaq9JQuGtRvG390XrpPaMmpDSdw9NjZcaM4ekKczEo5zJG~FGAjbh5fXsBv5AQbKmM5IfMfVj5AkOKnf0WvM~j7SlnCV6UMLMKzrpsHPmNNZKBxdRW8a7fPpRpCJ2VaT8TqHqdqhSBahwgV72w1W0A8CqHOUkLVDPZxlk0tEKp7Al7nFg__&Key-Pair-Id=APKAJE5CCD6X7MP6PTEA)
-