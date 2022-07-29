

returns the first Element within the document that matches the specified selector, or group of selectors. If no matches are found, `null` is returned.

## Finding the first element matching a class

In this example, the first element in the document with the class "`myclass`" is returned:

```javascript
var el = document.querySelector(".myclass");
```

## A more complex selector

Selectors can also be really powerful, as demonstrated in the following example. Here, the first `<input>` element with the name "_login_" (`<input name="login"/>`) located inside a `<div>` whose class is "user-panel main" (`<div class="user-panel main">`) in the document is returned:

```javascript
var el = document.querySelector("div.user-panel.main input[name='login']");
```

## Negation

As all CSS selector strings are valid, you can also negate selectors:

```javascript
var el = document.querySelector("div.user-panel:not(.main) input[name='login']");
```

This will select an input with a parent div with the user-panel class but not the main class.

---

- Reference:
  - [MDN](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector)
