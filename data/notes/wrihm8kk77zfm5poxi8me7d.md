

<center>
	<iframe width="560" height="315" src="https://www.youtube.com/embed/R8rmfD9Y5-c" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</center>

Given data:

```javascript
const items = [
    { name: 'Bike',     price: 100  },
    { name: 'TV',       price: 200  },
    { name: 'Album',    price: 10   },
    { name: 'Book',     price: 5    },
    { name: 'Phone',    price: 500  },
    { name: 'Computer', price: 1000 },
    { name: 'Keyboard', price: 25   }
]
```

## Reduce method

This is like wanting to get a sum of all the prices of your items that meet certain conditions.

Unlike the other methods the `reduce` method has 2 arguments and the first of which has to be the aggregate value holder

---

```javascript
const total = items.reduce((currentTotal, item) => {
    return item.price + currentTotal
}, 0)

console.log(total)
```

**Result:**

> 1840

we want to get a sum of all prices so we run the array method and  for each item in items we pass the item and a local variable in the arrow function to the function body.

at then end of the arrow function is a second argument for the `reduce` method which is where the `currentTotal` value should start. We probably want a total to start at 0 so that's where it is set to.

this is like a for loop using `item = item + newItem` 

so for each item passed to the function body, you also have the current running total passed as well. The items iteratively get returned and added to the `currentTotal` and then ultimately the `currentTotal` variable is returned giving you the sum of the array object's prices
