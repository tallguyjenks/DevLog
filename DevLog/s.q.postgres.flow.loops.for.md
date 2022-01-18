---
id: rKM3s9eOiZFkHhg7JFq3W
title: For
desc: ''
updated: 1642489688690
created: 1642489019775
---

```bash
for filename in *; do echo "put ${filename}"; done


for file in *; do 
    if [ -f "$file" ]; then 
        echo "$file" 
    fi 
```

for file in *.webm; do ffmpeg -i $file -vcodec libx264 -crf 24 "${file%.*}.mp4"
