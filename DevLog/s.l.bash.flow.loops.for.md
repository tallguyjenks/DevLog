---
id: rKM3s9eOiZFkHhg7JFq3W
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