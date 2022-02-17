---
id: 0rOwD0iryM6rWcxtvLZ4A
title: Container
desc: ''
updated: 1645136850564
created: 1645136824926
---

<https://docutils.sourceforge.io/docs/ref/rst/directives.html#container>

```rst
.. container:: custom

   This paragraph might be rendered in a custom way.
```

Parsing the above results in the following pseudo-XML:

```rst
<container classes="custom">
    <paragraph>
        This paragraph might be rendered in a custom way.
```
