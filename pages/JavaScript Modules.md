---
tags:
#  - 🌱️
#  - 🌞️
#  - 🌲️
aliases: 
  - Modules
  - Import
  - Export
cssclass: 
---

#### [[JavaScript Modules]]

---

## Modules

Prior to ES6, there were no native support for modules in JavaScript. Everything inside a JavaScript application, for example variables across different JavaScript files, shared the same scope.

ES6 introduces file based module, in which each module is represented by a separate `.js` file. Now, you can use the `export` or `import` statement in a module to export or import variables, functions, classes or any other entity to/from other modules or files.

This works in conjunction with [[JavaScript Variable Assignment|Variable Assignment]] options that came with ES6 to constrain variables to local scopes and not a global scope as well.

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

### [[ECMAScript 2020]]

#### Hot loading modules

```js
const baseModulePath = "./modules";
const btnBooks = document.getElementById("btnBooks");
let bookList = [];

btnBooks.addEventListener("click", async e => {
  const bookModule = await import(`${baseModulePath}/books.js`);

  bookList = bookModule.loadList();
});
```

So this code will only load the module on a particular click event, instead of a static declaration at the top of a file.

---

### ES6 Modules

[source](https://youtu.be/cRHQNNcYf6s?list=PLZlA0Gpn_vH-0FlQnruw2rd1HuiYJHHkm)

Importing sections of code so that files can be broken out into more modular files

---

2 types of exports, the default is the following at the end of a file:

`export default User`

this exports the User object as our default thing for the user.js file

the normal way of exports is:

`export { printName, printAge }`

which will export those two functions

an even better way would be inline like the example below for both the `User` class and functions: 

```javascript
export default class User {
    constructor(name, age) {
        this.name = name
        this.age = age
    }
}

export function printName(user) {
    console.log(`User's name is ${user.name}`)
}

export function printAge(user) {
    console.log(`User's is ${user.age} years old`)
}
```

Finally create a HTML file "`test.html`" and with the following code and open this HTML file in your browser using HTTP protocol (or use localhost). Also notice the `type="module"` on script tag.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <title>JavaScript ES6 Modules Demo</title>
</head>
<body>
    <script type="module" src="/examples/js/app.js"></script>
</body>
</html>
```

--- 

## You can only default export one thing so it will likely be the class you are defining if you are defining a class in your file 

Now in a new file we can `import` your `exported` items paying attention to your file paths in the import statements

`import User from '/user.js'`

this alone will throw an error, in your HTML where you source your javascript files you need to change the `script` tag to use ES6 modules:

`<script src="main.js"></script>`

`<script type="module" src="main.js"></script>`

a tip for the module import `<script>` tag was the `defer` keyword. Child issue: #6 

so now in a `*.js` file that does not have the User class declared in it, i can make and use the User class: 

```js
const user = new User('Bryan Jenks', 999)
console.log('user')
```

**Result:**

> User {name: "Bryan Jenks", age: 999}
> age: 999
> name: "Bryan Jenks"
> __proto__: Object

### Changing the names of the default import

so if you have a User [[JavaScript Classes|Class]] you're importing but in the new file you import that into you want to import that class but call it something different, then what you can do is basically treat it like a base class (which it is) and say:

`import U from '/user.js'`

because the User class is the default export its assuming we're saying something like this if we were in python

```python
import pandas as pd
```

except that its `import User as U`

### To import non-default things 

if we want the functions we defined in the `user.js` file and also exported, we can also import them with the following syntax:

```js
import U, { printName, printAge } from '/user.js'
```

basically, the default import can just be declared as `U` in this instance, where as non default imports have to be imported with the brace syntax. We can also change the name of those items too in this following was: 

```js
import U, { printName as printUsername, printAge as printUserAge } from '/user.js'
```

For more browser support a common method of dealing with imports is to use the `babel` tool to convert these newer features into older and supported javascript code

---
Tags: 

Reference:

Related:
- 
