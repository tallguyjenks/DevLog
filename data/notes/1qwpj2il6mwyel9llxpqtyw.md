

A JavaScript `Symbol` is a primitive datatype just like Number, String, or Boolean.

It represents a unique "_hidden_" identifier that no other code can accidentally access.

For instance, if different coders want to add a `person.id` property to a person object belonging to a third-party code, they could mix each others values.

Using `Symbol()` to create a unique identifiers, solves this problem:

```js
const person = {  
 firstName: "John",  
 lastName: "Doe",  
 age: 50,  
 eyeColor: "blue"  
};  
  
let id = Symbol('id');  
person.id = 140353;
```

Symbols are always unique.

If you create two symbols with the same description they will have different values.

```js
Symbol("id") == Symbol("id") // false
```
