

## New Number Properties

ES6 added the following properties to the Number object:

- `EPSILON`
- `MIN_SAFE_INTEGER`
- `MAX_SAFE_INTEGER`

```js
var x = Number.EPSILON;
console.log(x);
// 2.220446049250313e-16
var x = Number.MIN_SAFE_INTEGER;
console.log(x);
// 4 -9007199254740991
var x = Number.MAX_SAFE_INTEGER;
console.log(x);
// 6 9007199254740991
```
