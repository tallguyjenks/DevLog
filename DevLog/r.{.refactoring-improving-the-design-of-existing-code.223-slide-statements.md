---
id: 8wR4t7heXjSyxCjiYsEZu
title: 223 Slide Statements
desc: ''
updated: 1642626305891
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
