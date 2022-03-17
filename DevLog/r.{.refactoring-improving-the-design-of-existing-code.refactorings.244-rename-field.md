---
id: 1w0zdvscgsr44zr68us9rli
title: Rename Field
desc: ''
updated: 1647557425313
created: 1647556689580
---

```javascript
// BEFORE
class Organization {
  get name() {...}
}
// AFTER
class Organization {
  get title() {...}
}
```

- If the record has limited scope, rename all accesses to the field and test; no need to do the rest of the mechanics.
- If the record isn't already encapsulated, apply [[r.{.refactoring-improving-the-design-of-existing-code.refactorings.162-encapsulate-record]]
- Rename the private field inside the object, adjust internal methods to fit.
- If the constructor uses the name, apply [[r.{.refactoring-improving-the-design-of-existing-code.refactorings.124-change-function-declaration]] to rename it.
- Apply [[r.{.refactoring-improving-the-design-of-existing-code.refactorings.124-change-function-declaration]] to the accessors.
