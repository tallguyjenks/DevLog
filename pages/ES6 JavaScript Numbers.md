---
tags:
#  - 🌱️
#  - 🌞️
#  - 🌲️
aliases: 
  - Number.isSafeInteger()
  - Number.isInteger()
  - isSafeInteger()
  - isInteger()
  - isNaN()
  - isFinite() 
  - ES6 Number Properties
  - ES6 Number Methods
cssclass: 
---

#### [[ES6 JavaScript Numbers]]

---

## New Number Properties

ES6 added the following properties to the Number object:

- `EPSILON`
- `MIN_SAFE_INTEGER`
- `MAX_SAFE_INTEGER`

```js
var x = Number.EPSILON;
console.log(x);
var x = Number.MIN_SAFE_INTEGER;
console.log(x);
var x = Number.MAX_SAFE_INTEGER;
console.log(x);
```

## New Number Methods

ES6 added 2 new methods to the Number object:

-   `Number.isInteger()`
-   `Number.isSafeInteger()`


## The Number.isInteger() Method

The `Number.isInteger()` method returns `true` if the argument is an integer.

### Example

```js
Number.isInteger(10);        // returns true  
Number.isInteger(10.5);      // returns false
```

## The Number.isSafeInteger() Method

A safe integer is an integer that can be exactly represented as a *double precision number*.

The `Number.isSafeInteger()` method returns `true` if the argument is a safe integer.

### Example

```js
Number.isSafeInteger(10);    // returns true  
Number.isSafeInteger(12345678901234567890);  // returns false
```

Safe integers are all integers from 

**$-(2^{53} - 1)$** to **$+(2^{53} - 1)$**

This is safe: *9007199254740991*

This is not safe: *9007199254740992*

## New Global Methods

ES6 added 2 new global number methods:

-   `isFinite()`
-   `isNaN()`

## The isFinite() Method

The global `isFinite()` method returns `false` if the argument is `Infinity` or `NaN`.

Otherwise it returns `true`:

### Example

```js
isFinite(10/0);       // returns false  
isFinite(10/1);       // returns true 
```

[Try it Yourself »](https://www.w3schools.com/Js/tryit.asp?filename=tryjs_es6_isfinite)

## The isNaN() Method

The global `isNaN()` method returns `true` if the argument is `NaN`. Otherwise it returns `false`:

### Example

```js
isNaN("Hello");       // returns true
```

---
Tags: 

Reference:

Related:
- 
