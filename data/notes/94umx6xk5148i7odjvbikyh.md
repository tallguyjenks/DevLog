

## Cut clips of a video

```bash
ffmpeg -ss 0 -t 608 -i input.mkv output.mkv
```

`-ss` which are the start seconds of the clip
`-t` is how long the clip is to cut out so if we start at 0 and go until 608 seconds then it clips out a 10min8sec video out of what ever video we have. 
`-i` flags the next argument as an input file, there can be multiple.

_Alternative:_

```bash
ffmpeg -i input.mkv -ss 0 -t 10:08 -c copy output.mkv
```

In this alternative examples, 
`-i` the input file 
`-ss` start stream at 0 seconds and 
`-t` says the amount of time to go is 10min8sec then 
`-c` is codec its a copy this way it doesnt need to reencode it saving time, and then the output file.
