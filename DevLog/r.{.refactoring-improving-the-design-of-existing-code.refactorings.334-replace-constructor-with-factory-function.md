---
id: nmqnpgdeae0kizb5xtyrnsg
title: 334 Replace Constructor with Factory Function
desc: ''
updated: 1641268550142
created: 1641105063875
stub: false
isDir: false
---

```javascript
//FROM
leadEngineer = new Employee(document.leadEngineer, 'E');

//TO
leadEngineer = createEngineer(document.leadEngineer);
```
