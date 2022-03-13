---
id: 60ast1oy0wp58dbo4s424v3
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
