

## The object destructuring assignment

In ES5 to extract the property values of an object we need to write something like this:

```js
// ES5 syntax
var person = {name: "Peter", age: 28};

var name = person.name;
var age = person.age;

document.write(name); // Peter
document.write("<br>");
document.write(age); // 28
```

But in ES6, you can extract object's property values and assign them to the variables easily like this:

```js
// ES6 syntax
let person = {name: "Peter", age: 28};

let {name, age} = person; // Object destructuring assignment

document.write(name); // Peter
document.write("<br>");
document.write(age); // 28
```

---

- Reference:
  - <https://www.tutorialrepublic.com/javascript-tutorial/javascript-es6-features.php>
