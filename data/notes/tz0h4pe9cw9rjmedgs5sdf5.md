

## Making a GIF out of a video clip:

```shell
ffmpeg -i <VIDEO FILE> -pix_fmt rgb8 -r 8 -vf scale=-1:640 my-gif.gif
```
