

## Return the Quickest Completed item

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
