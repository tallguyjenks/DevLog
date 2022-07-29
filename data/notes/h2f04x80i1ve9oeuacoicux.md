
```bash
ffmpeg -i input.mkv -c copy output.m4v
```

## loop through a directory and convert all files of one type to the other

```bash
for file in *.mkv; do ffmpeg -i "${file}" -c copy "${file//.mkv/.mp4}"; done
```
