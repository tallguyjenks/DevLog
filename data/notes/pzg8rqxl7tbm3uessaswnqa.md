

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

## Map

Map will let you take an array and turn it into an entirely new array while also allowing you to perform operations upon it

---

```js
const itemPrice = items.map((item) => {
    return item.price + 100
})
```

in other languages map always reminded me of applying a function to each item in an array/vector so in this case it is

- take each item in items
- pass to arrow functions (the surgical table)
- operate upon it (add 100 to the item)
- build the return array
- assign the return array to the `itemPrices` constant which consists of the original array with each element having had its prices increased by 100
