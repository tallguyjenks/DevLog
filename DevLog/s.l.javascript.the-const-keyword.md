---
id: z5204w7p8gwoplnyjwn64b0
title: The Const Keyword
desc: ''
updated: 1641408109091
created: 1641105063914
stub: false
isDir: false
---


The `CONST` keyword is a way to assign a value to an immutable variable that respects local scoping.

```js
var x = 10;
// Here x is 10
{
  const x = 2;
  // Here x is 2
  x = 5;
  // ERROR: value cannot be re-assigned	
}
// Here x is 10
```
