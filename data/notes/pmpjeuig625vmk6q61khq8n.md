

## Array.findIndex()

The `findIndex()` method returns the **index** of the first array element that passes a test function.

This example finds the index of the first element that is larger than 18:

### Example

```js
var numbers = [4, 9, 16, 25, 29];  
var first = numbers.findIndex(myFunction);  
  
function myFunction(value, index, array) {  
  return value > 18;  
}

myFunction(25,3,numbers);
```
