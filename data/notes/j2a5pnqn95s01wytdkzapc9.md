

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

## Filtering items

```js
const filteredItems = items.filter((item) => {
    return item.price <= 100
})

console.log(filteredItems)
```

**Result:**

> .
> (3) ["Video 1 Recorded", "Video 2 Recorded", "Video 3 Recorded"]
> 0: "Video 1 Recorded"
> 1: "Video 2 Recorded"
> 2: "Video 3 Recorded"
> length: 3
> **proto**: Array(0)

Reading this like English, 

- The immutable variable `filteredItems` receives the following value(s). 
- The array of objects has the filter method applied
  - The filter uses an arrow function #2 that takes a single parameter `(item)`
  - The arrow function says "for each item in items, pass each item into my function body and operate upon it"
  - Inside the function body the items price attribute is operated on with basic arithmetic to determine if it meets the condition `<=` 
  - If true, the data is returned with all other valid data that met the condition as the `.filter` method is an array method and likely returns an array as a result
  - Each item that met the condition is then added to the resulting returned array 
- The returned array is then assigned to the constant variable `filteredItems`
