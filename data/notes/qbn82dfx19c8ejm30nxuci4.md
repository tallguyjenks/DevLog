

## Modules

Prior to ES6, there were no native support for modules in JavaScript. Everything inside a JavaScript application, for example variables across different JavaScript files, shared the same scope.

ES6 introduces file based module, in which each module is represented by a separate `.js` file. Now, you can use the `export` or `import` statement in a module to export or import variables, functions, classes or any other entity to/from other modules or files.

This works in conjunction with [[JavaScript Variable Assignment|s.l.javascript.variable-assignment]] options that came with ES6 to constrain variables to local scopes and not a global scope as well.

Let's create a module i.e. a JavaScript file "`main.js`" and place the following code in it:

```js
let greet = "Hello World!"; 
const PI = 3.14; 
function multiplyNumbers(a, b) {
	return a \* b; 
} 
// Exporting variables and functions 
export { greet, PI, multiplyNumbers };
```

Now create another JavaScript file "app.js" with the following code:

```js
import { greet, PI, multiplyNumbers } from './main.js'; 
alert(greet); 
// Hello World! 
alert(PI); 
// 3.14 
alert(multiplyNumbers(6, 15)); // 90
```
