

## The Number.isSafeInteger() Method

A safe integer is an integer that can be exactly represented as a _double precision number_.

The `Number.isSafeInteger()` method returns `true` if the argument is a safe integer.

### Example

```js
Number.isSafeInteger(10);    // returns true  
Number.isSafeInteger(12345678901234567890);  // returns false
```

Safe integers are all integers from 

**$-(2^{53} - 1)$** to **$+(2^{53} - 1)$**

This is safe: _9007199254740991_

This is not safe: _9007199254740992_
