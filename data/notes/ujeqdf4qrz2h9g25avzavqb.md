
## Info Fields

In python docstrings these might present as items in the docstrings

```rst
:param str name: optional name
```

- info is that it is a `parameter`
- follow by type `str`
- then the name of the param `name`
- and finally the description

This can also be borken out onto 2 different lines for legibility sake

```rst
:param name: optional name
:type name: str
```

```rst
:returns: 'Hello world!' or 'Hello, {name}!'
:rtype: str
```

![return types](/assets/images/2022-02-17-12-40-09.png)

`:attr block_size:` being used to document a class attribute

`:raises ValueError:` To define the exception it may raise and why it will raise that exception

![attributes and exceptions](/assets/images/2022-02-17-12-41-35.png)

`:meth:` for defining methods
