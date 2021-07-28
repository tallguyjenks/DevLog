---
tags:
#  - 🌱️
#  - 🌞️
#  - 🌲️
aliases: 
  - Promises
  - Promise
cssclass: 
---

#### [[JavaScript Promises]]

---

### Promises

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

### Callbacks (superceded by promises)

```js
const userLeft = false
const userWatchingCatMeme = false

function watchTutorialCallback(callback, errorCallback) {
    if (userLeft) {
        errorCallback({
            name: 'User Left',
            message: ':('
        })
    } else if (userWatchingCatMeme) {
        errorCallback({
            name: 'User Watching Cat Meme',
            message: 'WebDevSimplified < Cat'
        })
    } else {
        callback('Thumbs up and Subscribe')
    }
}

watchTutorialCallback((message) => {
    console.log('Success ' + message)
}, (error) => {
    console.log(error.name + ' ' + error.message)
}
```

Promises were meant to supercede callbacks and now the same code can be put into a promise:

```js
function watchTutorialPromise() {
    return new Promise((resolve, reject) => {
        if (userLeft) {
            reject({
                name: 'User Left',
                message: ':('
            })
        } else if (userWatchingCatMeme) {
            reject({
                name: 'User Watching Cat Meme',
                message: 'WebDevSimplified < Cat'
            })
        } else {
            resolve('Thumbs up and Subscribe')
        }
    })
}

watchTutorialPromise.then((message) => {
    console.log('Success ' + message)
}).catch((error) => {
    console.log(error.name + ' ' + error.message)
})
```

The code looks cleaner and to avoid lots of nested callbacks and "callback hell" you can just use this syntax to deal with multiple then actions

```js
watchTutorialPromise.then((message) => {
    console.log('Success ' + message)
}).then((message) => {
    console.log('Success ' + message)
}).catch((error) => {
    console.log(error.name + ' ' + error.message)
})
```

### Batching Promise Execution

```js
const recordVideoOne = new Promise((resolve, reject) => {
    resolve('Video 1 Recorded')
})
const recordVideoTwo = new Promise((resolve, reject) => {
    resolve('Video 2 Recorded')
})
const recordVideoThree = new Promise((resolve, reject) => {
    resolve('Video 3 Recorded')
})
```

run a bunch of promises all at once in parallel instead of sequentially. 
these promises all resolve and dont reject. 

```js
Promise.all([
    recordVideoOne,
    recordVideoTwo,
    recordVideoThree
]).then((messages) => {
    console.log(messages)
})
```

so once the promises resolve the `.then` will then return an array of messages from the promises that we can then log 

### Return the Quickest Completed item

`promise.all` waits for all of the promises to finish execution before returning results 
where as 
`promise.race` returns as soon as anything finishes and will return that first completed item in the `.then` so that an array isnt returned only a single result value of the quickest item because its a `.race`

```js
Promise.race([
    recordVideoOne,
    recordVideoTwo,
    recordVideoThree
]).then((message) => {
    console.log(message)
})
```


---
Tags: 

Reference:

Related:
- 
