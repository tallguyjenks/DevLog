

### Re-use command arguments

```bash
mkdir very-large-directory-name
cd very-large-directory-name
# Instead of duplicating the argument of the mkdir command, you can use !$ for retrieve the last argument of the last command, the result is:
mkdir very-large-directory-name
cd !$ # == cd very-large-directory-name
```
