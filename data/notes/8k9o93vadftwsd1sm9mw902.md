

```bash {cmd=true}
cd "${workspaceFolder}" && lsd -lA *.md | awk '{print $7,$10,$NF}' | grep "$(date +"%b %Y")" | awk '{print "[["$NF"]]"}'
```
