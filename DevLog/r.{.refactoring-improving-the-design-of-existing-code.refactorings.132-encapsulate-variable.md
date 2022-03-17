---
id: fqhrsfmqeevgl2xogi8lcmk
title: Encapsulate Variable
desc: ''
updated: 1647556683420
created: 1647555699029
---

```javascript
// BEFORE
let defaultOwner = {firstName: "Martin", lastName: "Fowler"};
// AFTER
let defaultOwnerData = {firstName: "Martin", lastName: "Fowler"};
export function defaultOwner()       {return defaultOwnerData;}
export function setDefaultOwner(arg) {defaultOwnerData = arg;}
```

Access your data through functions so that updating the variable is as simple as changing a single function rather than every instance of a variable used.

variables encapsulated by functinos are also testable
