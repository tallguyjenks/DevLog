

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

## Some method

this method returns a boolean value and is great for asking a question of your data and getting simple response in return.

---

```javascript
const hasInexpensiveItems = items.some((item) => {
    return item.price <= 100
})
```

**Result:**

> true

for each item in items, is there at least 1 item that is less than or equal to 100? if so return true, otherwise false. 
