---
id: fmbpyabn5iwy8fygqy7b70g
title: Object Entries
desc: ''
updated: 1641407998086
created: 1641105063912
stub: false
isDir: false
---


## JavaScript Object Entries

ECMAScript 2017 adds a new `Object.entries` method to objects:

### Example

```js
const person = {  
  firstName : "John",  
  lastName : "Doe",  
  age : 50,  
  eyeColor : "blue"  
};  
document.getElementById("demo").innerHTML = Object.entries(person);
```
