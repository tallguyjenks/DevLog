---
id: HPZXXnIQ8s0hYzgUk2G8z
title: Monthly Review Task Code Execution
desc: ''
updated: 1641626994991
created: 1641106669372
---

```bash {cmd=true}
cd "${workspaceFolder}" && lsd -lA *.md | awk '{print $7,$10,$NF}' | grep "$(date +"%b %Y")" | awk '{print "[["$NF"]]"}'
```
