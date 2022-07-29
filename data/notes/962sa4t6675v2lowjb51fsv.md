

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
> **proto**: Object
