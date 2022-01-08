---
tags: 💻️/Javascript
publish: true
aliases: 
  - const
  - The Const Keyword
cssclass: 
created: 2022-01-07 1714
updated: 2022-01-07 1714
---

# [[JavaScript The CONST Keyword]]

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

- Tags: 
	- 
- Reference:
	- 
- Related:
	- [[JavaScript The VAR Keyword|VAR]]
	- [[JavaScript The Let Keyword|LET]]
