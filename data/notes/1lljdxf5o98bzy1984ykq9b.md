

## Template Literals

Template literals provide an easy and clean way create multi-line strings and perform string interpolation. Now we can embed variables or expressions into a string at any spot without any hassle.

Template literals are created using back-tick (`` ` ` ``) (grave accent) character instead of the usual double or single quotes. Variables or expressions can be placed inside the string using the `${...}` syntax. Compare the following examples and see how much useful it is:

```js
// Simple multi-line string
let str = `The quick brown fox
	jumps over the lazy dog.`;

document.write(`<pre>${str}</pre>`);

// String with embedded variables and expression
let a = 10;
let b = 20;
let result = `The sum of ${a} and ${b} is ${a+b}.`;
document.write(result); // The sum of 10 and 20 is 30.
```
