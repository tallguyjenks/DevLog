---
id: 8wR4t7heXjSyxCjiYsEZu
title: 223 Slide Statements
desc: ''
updated: 1642626659087
created: 1641105063876
stub: false
isDir: false
---

```javascript
//FROM
const pricingPlan = retrievePricingPlan();
const order = retreiveOrder();
let charge;
const chargePerUnit = pricingPlan.unit;

//TO
const pricingPlan = retrievePricingPlan();
const chargePerUnit = pricingPlan.unit;
const order = retreiveOrder();
let charge;
```

> Code is easier to understand when things that are related to each other appear together. If several lines of code access the same data structure, it's best for them to be together rather than intermingled with code accessing other data structures. At its simplest, I use Slide Statements to keep such code together. A very common case of this is declaring and using variables. Some people like to declare all their variables at the top of a function. I prefer to declare the variable just before I first use it.
