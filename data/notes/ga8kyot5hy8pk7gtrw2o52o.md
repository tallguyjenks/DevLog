

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
