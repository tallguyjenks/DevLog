

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

## For Each

does not return anything, basically acts like a for loop and takes a function as an argument as what you will be doing with each value

> "for each item in items, do the thing"

```js
items.forEach((item) => {
    console.log(item.name)
})
```

**Result:**

Reading like English:

- for each item in the array object, pass it to the arrow function #2 
- for each item i receive, log it
- next item

no returned objects just pure action
