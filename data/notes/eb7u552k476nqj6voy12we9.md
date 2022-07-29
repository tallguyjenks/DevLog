

### Async

with `Async` the downloads happen concurrently and only the Javascript execution is treat synchronously 

![[95397297-b4c85f80-08b7-11eb-8a63-068446b52032.png)

`Async` will allow the javascript to also run after the document `onReady()` event maybe this is not what you want. `Async` will also vary when it is run as it can be variable based on network speeds. if order matters this will throw a wrench in the works as it can be executed whenever dependent on the users network conditions.
