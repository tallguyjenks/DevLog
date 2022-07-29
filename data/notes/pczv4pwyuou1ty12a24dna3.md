

### Stdin as a file argument

```bash
# Command expects a file:
wc file1 file2
# Instead of making a temp file to read in a little text use this to pass in
# text as a temp file to STDIN
wc file1 - file2 # waits for you to type input and you complete this process by using `CTRL+D` which inserts the EOF character
```
