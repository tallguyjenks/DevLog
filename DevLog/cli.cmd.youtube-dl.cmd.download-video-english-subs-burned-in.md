---
id: oj9aaueai1z3pfskkzhbgnd
title: Download Video English Subs Burned In
desc: ''
updated: 1641267442858
created: 1641267442858
---


## Download video with english subs written to the video file

Might have to change `en` to the desired language such as when the language is listed as `english` for subtitles

```bash
youtube-dl --write-sub --sub-lang en <URL>
# Combine the video file and subtitles with ffmpeg:
ffmpeg -i input_video_file.mp4 -vf subtitles=subtitled_file.english.srt output_file_name.mp4
```
