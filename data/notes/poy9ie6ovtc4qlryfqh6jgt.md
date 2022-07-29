

Arrow functions do not have their own `this`. They are not well suited for defining **object methods**.

Arrow functions are not hoisted. They must be defined **before** they are used.

Using `const` is safer than using `var`, because a function expression is always a constant value.

You can only omit the `return` keyword and the curly brackets if the function is a single statement. Because of this, it might be a good habit to always keep them:

```javascript
/*
    Source: https://youtu.be/h33Srr5J9nY?list=PLZlA0Gpn_vH-0FlQnruw2rd1HuiYJHHkm
*/

// Normal function
function sum(a, b) {
    return a + b
}

// if it can fit on 1 line these make the code more concise and legible
let sum2 = (a, b) => a + b

/**************************************************************************************/
function isPositive(number) {
    return number >= 0 
}

// Single parameter functions dont need parens on their args
let isPositive = number => number >= 0

/**************************************************************************************/

function randomNumber() {
    return Math.random
}

// No parameter functions need the parens to exist though
let randomNumber = () => Math.random

/**************************************************************************************/

// arrow functions really useful for anonymous functions
document.addEventListener('click', function(){
    console.log('click')
})

// is exactly the same as 

document.addEventListener('click', () => console.log('click'))

/**************************************************************************************/
/* 
    The real power of arrow functions is the redeffinition of the the 'this' keyword
    within them
*/

class Person {
    constructor(name) {
        this.name = name
    }
    printNameArrow() {
        setTimeout(() => {
            console.log('Arrow: ' + this.name)
        }, 100)
    }
    
    printNameFunction() {
        setTimeout(function() {
            console.log('Arrow: ' + this.name)
        }, 100)
    }
}

let person = new Person('Bob')
person.printNameArrow() // acts like most other programming langs
person.printNameFunction() // prints nothing because in normal functions the 'this' is defined based on WHERE the function is called
console.log(this.name) // also returns nothing as 'this' is not defined in the global scope

/*
    Normal functions redefine 'this' to what ever scope you function in and that is the global scope in this instance
    Arrow functions treat the scoping of the 'this' keyword like most other programming language now 
    its preferable now to use arrow function over normal functions unless explicitly necessary to use normal functions
*/
```

### Default Parameter Values

```js
function myFunction(x, y = 10) {  
  // y is 10 if not passed or undefined  
  return x + y;  
}  
myFunction(5); // will return 15
```
