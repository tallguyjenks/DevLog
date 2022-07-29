

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
