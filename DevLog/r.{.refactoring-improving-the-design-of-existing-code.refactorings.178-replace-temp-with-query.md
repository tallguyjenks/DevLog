---
id: m7yavwznmwqqechfmh719l0
title: 178 Replace Temp with Query
desc: ''
updated: 1642626219166
created: 1641105063875
stub: false
isDir: false
---

```javascript
//FROM
const basePrice = this._quantity * this._itemPrice;
if (basePrice > 1000)
    return basePrice * 0.95;
else
    return basePrice * 0.98;

//TO
get basePrice() {this._quantity * this._itemPrice;}

...

if (this.basePrice > 1000)
    return this.basePrice * 0.95;
else
    return this.basePrice * 0.98;
```
