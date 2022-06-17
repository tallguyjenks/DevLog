---
id: h2f04x80i1ve9oeuacoicux
title: Convert Video Formats
desc: ''
updated: 1655503249755
created: 1655501743169
---

```bash
ffmpeg -i input.mkv -c copy output.m4v
```

## loop through a directory and convert all files of one type to the other

```bash
for file in *.mkv; do ffmpeg -i "${file}" -c copy "${file//.mkv/.mp4}"; done
```
