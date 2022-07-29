

## Callbacks (superceded by promises)

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
