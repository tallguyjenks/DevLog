

The `let` keyword is a way to assign a value to a mutable variable that respects local scoping. 

```js
var x = 10;
// Here x is 10
{
  let x = 2;
  // Here x is 2
}
// Here x is 10
```
