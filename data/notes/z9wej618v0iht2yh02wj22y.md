

- [parse library for common string parsing](https://calmcode.io/parse/parse.html)

```python
from parse import parse

githubs = [
  "https://github.com/koaning/justcharts/",
  "https://github.com/koaning/human-learn/",
  "https://github.com/r1chardj0n3s/parse/",
]

[parse("https://github.com/{owner}/{repo}/", url).named for url in githubs]

# RESULTS:
[
{'owner': 'koaning', 'repo': 'justcharts'},
{'owner': 'koaning', 'repo': 'human-learn'},
{'owner': 'r1chardj0n3s', 'repo': 'parse'}
]

```

```python
1625696365632
from parse import search

fmt = "https://github.com/{account}/{project}/"
txt = "https://github.com/koaning/human-learn/ https://github.com/koaning/scikit-lego/"

# This only returns one result.
search(fmt, txt)
```

```python
from parse import findall

fmt = "https://github.com/{account}/{project}/"
txt = "https://github.com/koaning/human-learn/ https://github.com/koaning/scikit-lego/"
res = findall(fmt, txt)

# This returns two results
list(res)
```

```python
from parse import compile

p = compile("https://github.com/{account}/{project}/")

txt = "https://github.com/koaning/scikit-lego/"
p.parse(txt)

txt = "foo https://github.com/koaning/scikit-lego/"
p.search(txt)

txt = "https://github.com/koaning/scikit-lego/ https://github.com/koaning/scikit-lego/"
p.findall(txt)
```
