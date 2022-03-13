---
id: c1h4zbzqkb50wpdpc5pmvga
title: Multiple Docs in Single File
desc: ''
updated: 1645151063046
created: 1645151063046
---


## Multiple YAML Docs in a single file

In YAML the compile sees `---` as a separator between 2 different YAML documents

```yaml
name: "File one"
age: "one day"
planet: "earth"
---
name: "File two"
age: "two billion light years"
planet: "Jupiter"
```
