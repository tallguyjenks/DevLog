---
id: 7OTECkLTF9RZB3pi74Ggv
title: 310 Parameterize Function
desc: ''
updated: 1642628091710
created: 1642628011318
---

```javascript
//FROM
function tenPercentRaise(aPerson) {
  aPerson.salary = aPerson.salary.multiply(1.1);
}
function fivePercentRaise(aPerson) {
  aPerson.salary = aPerson.salary.multiply(1.05);
}


//TO
function raise(aPerson, factor) {
  aPerson.salary = aPerson.salary.multiply(1 + factor);
}
```
