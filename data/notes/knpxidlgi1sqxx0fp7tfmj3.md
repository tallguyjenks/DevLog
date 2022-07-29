
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
