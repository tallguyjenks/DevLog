---
id: a9oap1sn8d14pap0qeqhm2m
title: Formatting File Names
desc: ''
updated: 1641267391477
created: 1641267391477
---


## Formatting filenames of downloaded playlist:

```bash
youtube-dl --format mp4 -o "%(upload_date)s %(title)s by %(uploader)s.%(ext)s" <URL>
```
