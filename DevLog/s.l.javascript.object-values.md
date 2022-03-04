---
id: pu4yimnr7cxq6hj6n6xibeg
title: Object Values
desc: ''
updated: 1641408003973
created: 1641105063912
stub: false
isDir: false
---


## JavaScript Object Values

`Object.values` are similar to `Object.entries`, but returns a single dimension array of the object values:

### Example

```js
const person = {  
  firstName : "John",  
  lastName : "Doe",  
  age : 50,  
  eyeColor : "blue"  
};  
document.getElementById("demo").innerHTML = Object.values(person);
```
