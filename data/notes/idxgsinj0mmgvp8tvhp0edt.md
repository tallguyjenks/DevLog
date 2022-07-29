

## The Rest Parameters

This is similar to the function ellipsis parameter in [[R|r]] where the number of inputs in variable and you want to accept them all as a variable size [[Python Data Structures|python-data-structures#List]]/Array.

The rest parameter (`...`) allows a function to treat an indefinite number of arguments as an array:

```js
function sum(...args) {  
 let sum = 0;  
 for (let arg of args) sum += arg;  
 return sum;  
}  
  
let x = sum(4, 9, 16, 25, 29, 100, 66, 77);
```
