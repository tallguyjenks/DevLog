

### Ignore the first N lines

> By default, the tail command will show the last n rows, but if you specified the option -n with a number that starts with the + symbol, like +5 , the first 5 lines are going to be skipped.

```bash
# In this example, the tail command is going to skip the first 10 lines and print the rest of the file content.
tail -n +10 dataset.csv
```
