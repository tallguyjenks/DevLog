

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
