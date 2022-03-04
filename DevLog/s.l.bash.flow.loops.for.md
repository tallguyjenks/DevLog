---
id: 88a5zzwpujtg626odf4mv8x
title: For
desc: ''
updated: 1642491197903
created: 1642489019775
---


```bash
for filename in *; do echo "put ${filename}"; done


for file in *; do 
    if [ -f "$file" ]; then 
        echo "$file" 
    fi 
```
