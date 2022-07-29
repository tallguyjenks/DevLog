

### In General Code

- `__annotations__` gets a returned dictionary of type annotations for the object
- `class.__bases__` The tuple of base classes of a class object.
- `__builtins__` <https://newbedev.com/python-what-s-the-difference-between-builtin-and-builtins>
- `__cached__`  is the path to any compiled version of the code
- `instance.__class__` The class to which a class instance belongs.
- _R_ `__closure__` `None` or a tuple of cells that contain bindings for the function’s free variables.
- `__code__` The code object representing the compiled function body.
- `__defaults__` A tuple containing default args values for those args that have defaults, or `None`
- `object.__dict__` The namespace supporting arbitrary function attributes.
- `__doc__` The function’s documentation string, or None if unavailable; not inherited by subclasses.
- `__file__` The absolute path to the file that the code currently executing is within
- _R_ `__globals__` A reference to the dict that holds the function’s global vars 
  - the global namespace of the module in which the function was defined.
- `__import__` will return the top level module of a package, unless you pass a nonempty `fromlist` arg
- `__kwdefaults__` A dict containing defaults for keyword-only parameters.
- `__loader__` <https://stackoverflow.com/questions/22185888/pythons-loader-what-is-it>
- `__main__` The Entry point to a program, used in `if __name__ == "__main__":`
- `__module__` The name of the module the function was defined in, or None if unavailable.
- `__mro__` [https://docs.python.org/3/library/stdtypes.html#class.\_\_mro\_\_](https://docs.python.org/3/library/stdtypes.html#class.__mro__)
- `__name__` The function’s name. same as `__qualname__` but not showing the parents
- `__package__` <https://stackoverflow.com/a/21233334/12339658>
- `__path__` <https://stackoverflow.com/a/2700924/12339658>
- `__qualname__` A dotted name showing the “path” from the global scope to an item in that module
- `__spec__` `None` in `__main__` or interactive mode otherwise, information about the module
- `class.__subclasses__()` Returns a list of weak references to its immediate alive subclasses.
