

```bash
for filename in *; do echo "put ${filename}"; done

for file in *; do 
    if [ -f "$file" ]; then 
        echo "$file" 
    fi 
```
