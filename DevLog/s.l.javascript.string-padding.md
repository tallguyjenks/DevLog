---
id: o4avm8l4rl2lmk6bi7ccrn6
title: String Padding
desc: ''
updated: 1641408059736
created: 1641105063913
stub: false
isDir: false
---


## JavaScript String Padding

ECMAScript 2017 added two String methods: `padStart` and `padEnd` to support padding at the beginning and at the end of a string.

### Example

```js
let str = "5";  
str = str.padStart(4,0);  
// result is 0005
//========================//
let str = "5";  
str = str.padEnd(4,0);  
// result is 5000
```
