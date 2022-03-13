---
id: mcxh7olp691ivt2kwa5atyo
title: 154 Split Phase
desc: ''
updated: 1642626132627
created: 1641105063876
stub: false
isDir: false
---

```javascript
//FROM
const orderDate = orderString.split(/\s+/);
const productPrice = priceList[orderData[0].split("-")[1]];
const orderPrice = parseInt(orderData[1]) * productPrice;

//TO
const orderRecord = parseOrder(order);
const orderPrice = price(orderRecord, priceList);

function parseOrder(aString) {
    const values =  aString.split(/\s+/);
    return ({
        productID: values[0].split("-")[1],
        quantity: parseInt(values[1]),
    });
}
function price(order, priceList) {
    return order.quantity * priceList[order.productID];
}
```
