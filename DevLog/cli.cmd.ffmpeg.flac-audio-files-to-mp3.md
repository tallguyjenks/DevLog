---
id: 1qzq7zfu10z7xurs31lf6v5
title: Flac Audio Files to Mp3
desc: ''
updated: 1641184369128
created: 1641184369128
---


## Convert flac audio files to mp3

```shell
ffmpeg -i input.flac -ab 320k -map_metadata 0 -id3v2_version 3 output.mp3
```
