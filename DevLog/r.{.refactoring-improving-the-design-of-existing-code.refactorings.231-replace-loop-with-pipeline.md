---
id: wb8oig0e52do3z20hypyu6w
title: 231 Replace Loop with Pipeline
desc: ''
updated: 1642626735475
created: 1641105063875
stub: false
isDir: false
---

```javascript
//FROM
const names = [];
for (const i of input) {
    if (i.job === "programmer")
        names.push(i.name);
}

//TO
const names = input
    .filter(i => i.job === "programmer")
    .map(i => i.name)
;
```
