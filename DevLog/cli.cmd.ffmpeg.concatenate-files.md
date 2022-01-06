---
id: UqIrL9UrWzO7NxUrM3bAm
title: Concatenate Files
desc: ''
updated: 1641184295466
created: 1641184279802
---

## File Concatenation

This is what i used to concatenate multiple files together:

```bash
ffmpeg -f concat -i files.txt -c copy rsyncFullVideo.mkv
```

the `files.txt` portion is a list of all the files in their relevant directories wrapped in single quotes with the word "file" preceding each line like this:

```
File '~/Movie1.mkv'
File '~/Movie2.mkv'
File '~/Movie3.mkv'
```

after the `copy` command you list the output file/path/extention all of that and it works!

```bash
$ cat mylist.txt
file '/path/to/file1'
file '/path/to/file2'
file '/path/to/file3'

$ ffmpeg -f concat -i mylist.txt -c copy output.mp4
```
