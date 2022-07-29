

## Promises

> "Im going to give you the best video on promises"

---

```js
let p = new Promise((resolve, reject) => {
    let a = 1 + 1
    if (a == 2) {
        resolve('Success')
    } else {
        reject('Failed')
    }
}) 
```

1+1 will always = 2 so the `resolve()` method is called.

so if the promise is going to be resolved and we keep our promise of delivering a great video, **THEN** we resolve the promise.

this is also basically a try catch block but without the finally

```js
p.then((message) => {
    console.log('This is in the then' + message)
}).catch((message) => {
    console.log('This is in the catch' + message)
})
```

Promises are things you want to happen in the background but that take a long time.
like downloading an image in a server and not making other things wait for it.

---
