

- Reference: [This Tweet](https://twitter.com/simonw/status/1406336417500860423)

```bash
pip install textual
python -m textual.app
```

- Windows Error:

```
Traceback (most recent call last):
File "C:\Users\bjenks\AppData\Local\Programs\Python\Python39\lib\runpy.py", line 197, in _run_module_as_main
  return _run_code(code, main_globals, None,
File "C:\Users\bjenks\AppData\Local\Programs\Python\Python39\lib\runpy.py", line 87, in _run_code
  exec(code, run_globals)
File "C:\Users\bjenks\AppData\Local\Programs\Python\Python39\lib\site-packages\textual\app.py", line 19, in <module>
  from .driver import Driver
File "C:\Users\bjenks\AppData\Local\Programs\Python\Python39\lib\site-packages\textual\driver.py", line 8, in <module>
  import curses
File "C:\Users\bjenks\AppData\Local\Programs\Python\Python39\lib\curses\__init__.py", line 13, in <module>
  from _curses import *
ModuleNotFoundError: No module named '_curses'
```
