---
id: 4vf36l8mnmwius8ifdsk6l7
title: Get the Last Argument of the Last Run Command in Your Shell
desc: ''
updated: 1641270605607
created: 1641168992641
stub: false
isDir: false
---


- `URL:` <https://youtu.be/vt-IvdFP5ZA>
- `Channel/Host:` nick-janetakis
- `Publish Date:` 2021.12.07
- `Reviewed Date:` 2021.12.07

---

<center><iframe width="560" height="315" src="https://www.youtube.com/embed/vt-IvdFP5ZA" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></center>

---

- `$_` will give you the last argument of the last run command:

```bash
mkdir testDir
echo "$_"
#> testDir
```

- `${_}` runs the last run command

