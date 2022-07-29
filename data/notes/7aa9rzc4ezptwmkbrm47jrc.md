

- [article on logging for a python app](https://towardsdatascience.com/the-reusable-python-logging-template-for-all-your-data-science-apps-551697c8540)
- [Official Docs](https://docs.python.org/3/library/logging.html#)
- The level of the logger:

| Level    | Numberic Value |
| -------- | -------------- |
| NOTSET   | 0              |
| DEBUG    | 10             |
| INFO     | 20             |
| WARNING  | 30             |
| ERROR    | 40             |
| CRITICAL | 50             |

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

- From [Calm Code Rich Logging](https://calmcode.io/logging/rich.html) only for the stream handler not the file handler

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
