

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
