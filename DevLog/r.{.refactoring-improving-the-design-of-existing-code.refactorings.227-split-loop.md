---
id: 0jbmcf4ij6t6jrw8iptbvhc
title: 227 Split Loop
desc: ''
updated: 1642626695604
created: 1641105063876
stub: false
isDir: false
---

```javascript
//FROM
let averageAge = 0;
let totalSalary = 0;
for (const p of people) {
    averageAge += p.age;
    totalSalary += p.salary;
}
averageAge = averageAge / people.length;

//TO
let totalSalary = 0;
for (const p of people) {
    totalSalary += p.salary;
}

let averageAge = 0;
for (const p of people) {
    averageAge += p.age;
}
averageAge = averageAge / people.length;
```
