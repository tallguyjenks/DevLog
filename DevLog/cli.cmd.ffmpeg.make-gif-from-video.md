---
id: tz0h4pe9cw9rjmedgs5sdf5
title: Make Gif from Video
desc: ''
updated: 1641184338599
created: 1641184338599
---


## Making a GIF out of a video clip:

```shell
ffmpeg -i <VIDEO FILE> -pix_fmt rgb8 -r 8 -vf scale=-1:640 my-gif.gif
```
