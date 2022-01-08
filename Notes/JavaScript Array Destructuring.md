---
tags: 💻️/Javascript
publish: true
aliases: 
  - Array Destructuring
cssclass: 
created: 2022-01-07 1719
updated: 2022-01-07 1720
---

# [[JavaScript Array Destructuring]]

---

```js
// Before:
var width = 200;
var height = 400;

// After:
let [width, height] = [200, 400];

// before: 
const calculateArea = (areaParameters) => areaParameters[0] * areaParameters[1]
calculateArea([200, 400]);

// or for better naming in older functions:
const calculateArea = ([width, height]) => width * height
calculateArea([200, 400]);
```

---

- Tags: 
	- 	
- Reference:
	- 	
- Related:
	- [[Python Data Structures#List]]
