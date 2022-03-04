---
id: i9ifmetjexuk4jb8ydmh9ns
title: Globbing Vs Ls
desc: ''
updated: 1641452267646
created: 1641429174025
---


##### Use globbing instead of  ls

Instead of using `ls -l <pattern>` to return a wildcard glob, use the wildcard as it is and avoid `ls`

```bash
#  Documentation
pattern="ex*"

printf '%s\n' $pattern   # not ``ls -1 $pattern''
# > file1.txt
# > file_other.txt

for file in $pattern; do  # definitely, definitely not ``for file in $(ls $pattern)''
	printf 'Found file: %s\n' "$file"
done
# > Found file: file1.txt
# > Found file: file_other.txt
```

###### Documentation

- [parsing file globs with ls](https://mywiki.wooledge.org/ParsingLs)
- <https://superuser.com/questions/31464/looping-through-ls-results-in-bash-shell-script#31466>
