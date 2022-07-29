

## Batching Promise Execution

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
