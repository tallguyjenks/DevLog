

- `Author:` Sergio Daniel Cortez Chavez
- `Link:` <https://sergiocortez-37830.medium.com/linux-shell-tricks-2f34c5935b89>
- `Publish Date:` 2021.11.29
- `Reviewed Date:` [[log.daily.2021.12.20]]

---

## Stdin as a file argument

```bash
# Command expects a file:
wc file1 file2
# Instead of making a temp file to read in a little text use this to pass in
# text as a temp file to STDIN
wc file1 - file2 # waits for you to type input and you complete this process by using `CTRL+D` which inserts the EOF character
```

## Use the output of another command as a file argument

```bash
wc file1 <(echo “hello world”) file2
```

> When you wrap a command with `<(...)` bash generate a temporal file in a path like `/dev/fd/64`, then execute your wrapped command, put the output in this temporal file, and finally replace `<(...)` with the filename of the temporal file, in this case, `/dev/fd/64`

## Avoid conflicts with filenames that start with a dash

```bash
# -- indicates the end of the options section
# -myFile.txt uses a dash after the options section to avoid conflicts
cat -- -myFile.txt
```

## Re-run commands

```bash
# of course there's
sudo !!
# but you can also do
!-N # where N is the Nth command (Relative)
# or
!N # for the N command in your history (Absolute)
```

## Re-use command arguments

```bash
mkdir very-large-directory-name
cd very-large-directory-name
# Instead of duplicating the argument of the mkdir command, you can use !$ for retrieve the last argument of the last command, the result is:
mkdir very-large-directory-name
cd !$ # == cd very-large-directory-name
```

## Ignore the first N lines

> By default, the tail command will show the last n rows, but if you specified the option -n with a number that starts with the + symbol, like +5 , the first 5 lines are going to be skipped.

```bash
# In this example, the tail command is going to skip the first 10 lines and print the rest of the file content.
tail -n +10 dataset.csv
```

## Track the content of a log file

> See the contents of a file in real time

```bash
watch cat log.txt
```

> Although this command does the job, it is not the best option. You can use the tail command with the -f option to track only the new lines that are appended to the file,

