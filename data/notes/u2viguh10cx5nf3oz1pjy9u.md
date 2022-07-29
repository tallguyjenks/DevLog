
## Resources

- [Sphinx Tutorial][1]
- [reStructuredText Primer][2]
- [Sphinx Markup Constructs][3]
- [Sphinx Domains][4]

[1]: http://www.sphinx-doc.org/en/stable/tutorial.html
[2]: http://www.sphinx-doc.org/en/stable/rest.html
[3]: http://www.sphinx-doc.org/en/stable/markup/index.html
[4]: http://www.sphinx-doc.org/en/stable/domains.html

## Quick Start

```bash
pip install Sphinx
mkdir docs
cd docs
sphinx-quickstart
```

This creates:

![quick start](/assets/images/2022-02-17-12-49-53.png)

## Versioning

Instead of hardcoding version in the quick start wizard, use the python `__version__` dunder to have the version automatically be pulled.

![version](/assets/images/2022-02-17-12-51-56.png)

## Building The docs

```bash
sphinx-build . _build/html/
make html # this is just an alias to the above command
```

Instead of just detecting changes you might want to rebuild the whole thing:

```bash
sphinx-build -E . _build/html/
make clean; make html
```

### Code Coverage

can use a different build tool addon that is activated from the quickstart wizard called `coverage`

```bash
sphinx-build -b coverage . _build/coverage/`
```

This will use `coverage` as the build tool and tell you when you have undocumented functions. Otherwise sphinx will fail quietly because if there's no work to do (functions dont have doc strings) then it fails quietly.

There is a flag to get it to process and render function documentation even if its blank called `undock members` but coverage gives insight into undocumented things.

## Themes

```bash
pip install sphinx_rtd_theme # this is for read the docs theme
```

and then inside `conf.py` in the `docs/` directory:

```python
html_theme = 'sphinx_rtd_theme'
```
