
```javascript
//FROM
function circum(radius) {...}

//TO
function circumference(radius) {...}
```

If deprecating something like API code a useful way of accomplishing that easily might be to do something like this:

```javascript
//FROM
function circum(radius) {
	return Math.PI * 2 * radius;
}

//TO
function circum(radius) {
	console.log("This function is deprecated, please use circumference()");
	return circumference(radius);
}

function circumference(radius) {
	return Math.PI * 2 * radius;
}
```

This also makes it easy to refactor in place and only change small things like what the contents are of `circum()` this way if it breaks code we can just handle it in our new function body and all references to `circum()` are intact until we're able to migrate everything to the new function declaration.
