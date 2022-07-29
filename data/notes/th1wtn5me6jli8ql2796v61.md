
```javascript
// BEFORE
let a = height * width;
// AFTER
let area = height * width;
```

- Single line lambda functions where the variable is easy to track are fine with single letters
- variables that live in functions are also likely fine to be terse
- Variables used throughout should be descriptive and if the variable is used widely, consider [[r.{.refactoring-improving-the-design-of-existing-code.refactorings.132-encapsulate-variable]]
