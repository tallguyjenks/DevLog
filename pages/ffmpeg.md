## File Concatenation

This is what i used to concatenate multiple files together:

```bash
ffmpeg -f concat -i files.txt -c copy rsyncFullVideo.mkv
```

the `files.txt` portion is a list of all the files in their relevant directories wrapped in single quotes with the word "file" preceding each line like this:

File '~/Movie1.mkv'

File '~/Movie2.mkv'

File '~/Movie3.mkv'

after the `copy` command you list the output file/path/extention all of that and it works!

```bash
$ cat mylist.txt
file '/path/to/file1'
file '/path/to/file2'
file '/path/to/file3'

$ ffmpeg -f concat -i mylist.txt -c copy output.mp4
```
- ## Cut clips of a video
  
  ```bash
  ffmpeg -ss 0 -t 608 -i input.mkv output.mkv
  ```
  
  The arguments in this are `-ss` which are the start seconds of the clip, `-t` is how long the clip is to cut out so if we start at 0 and go until 608 seconds then it clips out a 10min8sec video out of what ever video we have. `-i` flags the next argument as an input file, there can be multiple.
  
  *Alternative:*
  
  ```bash
  ffmpeg -i input.mkv -ss 0 -t 10:08 -c copy output.mkv
  ```
  
  In this alternative examples, the input file is determined first with `-i`, then the input file, `-ss` start stream at 0 seconds and `-t` says the amount of time to go is 10min8sec then `-c` is codec its a copy this way it doesnt need to reencode it saving time, and then the output file.
- ## Resources
  
  [VERY helpful stack overflow Q/A that answered this for me](https://stackoverflow.com/questions/7333232/how-to-concatenate-two-mp4-files-using-ffmpeg)
- ## Making a GIF out of a video clip:
  
  
  `ffmpeg -i <VIDEO FILE> -pix_fmt rgb8 -r 8 -vf scale=-1:640 my-gif.gif`
- ## Compress video with no quality loss
  
  `ffmpeg -i input.mkv -vcodec libx264 -crf 24 output.mp4`
- ## Convert flac audio files to mp3
  
  `ffmpeg -i input.flac -ab 320k -map_metadata 0 -id3v2_version 3 output.mp3`