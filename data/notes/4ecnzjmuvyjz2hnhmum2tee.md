

## The Spread Operator

The spread operator, which is also denoted by (`...`), performs the exact opposite function of the rest operator. The spread operator spreads out (i.e. splits up) an array and passes the values into the specified function, as shown in the following example:

```js
function addNumbers(a, b, c) {
	return a + b + c;
}

let numbers = [5, 12, 8];

// ES5 way of passing array as an argument of a function
document.write(addNumbers.apply(null, numbers)); // 25
document.write("<br>");

// ES6 spread operator
document.write(addNumbers(...numbers)); // 25
```

The spread operator can also be used to insert the elements of an array into another array without using the array methods like `push()`, `unshift()` `concat()`, etc.

```js
let pets = ["Cat", "Dog", "Parrot"];
let bugs = ["Ant", "Bee"];

// Creating an array by inserting elements from other arrays
let animals = [...pets, "Tiger", "Wolf", "Zebra", ...bugs];

document.write(animals); // Cat,Dog,Parrot,Tiger,Wolf,Zebra,Ant,Bee
```
