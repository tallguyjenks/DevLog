

## Write Subtitles to a video file

```shell
yt-dlp <URL>
yt-dlp --write-sub --convert-subs srt <URL>
ffmpeg -i video.webm -i subtitles.srt -c:v copy -c:s copy output.mkv
```
