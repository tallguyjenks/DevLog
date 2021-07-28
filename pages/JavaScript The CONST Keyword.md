---
tags:
aliases: 
  - const
  - The Const Keyword
cssclass: 
---

#### [[JavaScript The CONST Keyword]]

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

---
Tags: 

Reference:

Related:
- [[JavaScript The VAR Keyword|VAR]]
- [[JavaScript The Let Keyword|LET]]
