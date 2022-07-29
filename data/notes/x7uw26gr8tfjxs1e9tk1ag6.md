

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
