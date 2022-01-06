---
id: sqzoUYlSeMiyVuvbhql8p
title: Formatting File Names
desc: ''
updated: 1641267391477
created: 1641267391477
---

## Formatting filenames of downloaded playlist:

```bash
youtube-dl --format mp4 -o "%(upload_date)s %(title)s by %(uploader)s.%(ext)s" <URL>
```
