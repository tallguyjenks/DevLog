---
id: tb0scmsbt0yxf93rqs20r6r
title: For of Loop
desc: ''
updated: 1641407061381
created: 1641105063911
stub: false
isDir: false
---


## The `for...of` Loop

The new `for...of` loop allows us to iterate over arrays or other iterable objects very easily. 

Also, the code inside the loop is executed for each element of the iterable object. Here's an example:

```js
// Iterating over array 
let letters = ["a", "b", "c", "d", "e", "f"]; 

for(let letter of letters) { 
	console.log(letter); // a,b,c,d,e,f 
}
// Iterating over string 
let greet = "Hello World!"; 

for(let character of greet) { 
	console.log(character); // H,e,l,l,o, ,W,o,r,l,d,! 
}
```

---

- Reference:
  - <https://www.tutorialrepublic.com/javascript-tutorial/javascript-es6-features.php>

