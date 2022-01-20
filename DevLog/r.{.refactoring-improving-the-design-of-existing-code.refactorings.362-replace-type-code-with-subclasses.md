---
id: EqHNbN9XW28PYM1RxLhJ6
title: 362 Replace Type Code with Subclasses
desc: ''
updated: 1642627263013
created: 1641105063876
stub: false
isDir: false
---

```javascript
//FROM
function createEmployee(name, type) {
    return new Employee(name, type);
}

//TO
function createEmployee(name, type) {
    switch (type) {
        case "engineer": return new Engineer(name);
        case "salesman": return new Salesman(name);
        case "manager":  return new Manager (name);
    }
```
