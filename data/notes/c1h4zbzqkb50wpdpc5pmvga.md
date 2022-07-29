

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
