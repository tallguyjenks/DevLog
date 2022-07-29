

## Array.find()

The `find()` method returns the **value** of the first array element that passes a test function.

This example finds (returns the value of ) the first element that is larger than 18:

### Example

```js
var numbers = [4, 9, 16, 25, 29];  
var first = numbers.find(myFunction);  
  
function myFunction(value, index, array) {  
 return value > 18;  
}

myFunction(25,3,numbers); // TRUE
```

```js
const items = [
    { name: 'Bike',     price: 100  },
    { name: 'TV',       price: 200  },
    { name: 'Album',    price: 10   },
    { name: 'Book',     price: 5    },
    { name: 'Phone',    price: 500  },
    { name: 'Computer', price: 1000 },
    { name: 'Keyboard', price: 25   }
]

const foundItem = items.find((item) => {
    return item.name === 'Book'
})

console.log(foundItem)
```

> {name: "Book", price: 5}
>
> name: "Book"
>
> price: 5
>
> **proto**: Object
>
