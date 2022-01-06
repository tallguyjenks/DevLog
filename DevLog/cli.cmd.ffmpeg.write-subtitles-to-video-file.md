---
id: Kdd7vARZOXJ7u6By4GCgY
title: Write Subtitles to Video File
desc: ''
updated: 1641184383191
created: 1641184383191
---

## Write Subtitles to a video file

```shell
yt-dlp <URL>
yt-dlp --write-sub --convert-subs srt <URL>
ffmpeg -i video.webm -i subtitles.srt -c:v copy -c:s copy output.mkv
```
