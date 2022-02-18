---
id: FWy6bBAZYW0nom4MAREZt
title: Tips Tricks
desc: ''
updated: 1645150800931
created: 1645150398446
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

## Multi-line strings

### Literal Block

This preserves the `\n` character at the end of each line, such as in a list of executed CLI commands

```yaml
script: |
    echo "hello world" > file.txt
    cat file.txt
    sed s/hello/Hello/g file.txt > file2.txt
    mv file2.txt file.txt
```

### Folded Block Approach

This treats the text as a single run on sentance with no new lines akin to: 

`script: Hello there This is some text but will be on the same line as the previous text`

```yaml
script: >
    Hello there
    This is some text
    but will be on the same line as the previous text
```

## Explicit Tags

For data type casting

```yaml
numbers:
    num1: !!int 1.0 # converted to 1
    num2: !!float 100 # converted to 100.0
    num3: !!str 150 # converted to "150"
```

## Anchors



```yaml
man:
  name: Utibe
  age: 1000
  galaxy: milky-way
  dinosaursExist: no
alien:
  name: kal-el
  age: 10000000
  galaxy: milky-way
  dinosaursExist: no
names:
  - Utibe
  - kal-el
```


