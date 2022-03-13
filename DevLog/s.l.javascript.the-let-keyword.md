---
id: kx492rux5lhwuzaf754uqzn
title: The Let Keyword
desc: ''
updated: 1641408115988
created: 1641105063914
stub: false
isDir: false
---


The `let` keyword is a way to assign a value to a mutable variable that respects local scoping. 

```js
var x = 10;
// Here x is 10
{
  let x = 2;
  // Here x is 2
}
// Here x is 10
```
