

### File Handling

#### Using Temp Files With Bash

- Temp files are stored in the `/tmp/` directory and will need to be removed upon script completion. Why use a temp file or directory? Because it will make it easier to have a storing place of a file that holds some information you want to be read, or just act as an intermediary file/directory.

```bash
#  Documentation
# All temp files need those X's for randomization
# check out `man mktemp` for more details
tmpfile=$(mktemp /tmp/abc-script.XXXXXX)

# <CODE>

rm "$tmpfile"
```

##### Documentation

- [SO answer](https://unix.stackexchange.com/questions/181937/how-create-a-temporary-file-in-shell-script)
