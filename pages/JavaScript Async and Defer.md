---
tags:
aliases: 
  - Async 
  - Defer
cssclass: 
---

#### [[JavaScript Async and Defer]]

---

### Async and Defer

<center>
	<iframe width="560" height="315" src="https://www.youtube.com/embed/BMuFBYw91UQ" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</center>


Normal DOC parsing is that is parses synchronously, so as soon as it hits a `<script>` tag it stops and downloads that content first and then executes it and only THEN continues with the HTML download/parsing.

#### Async

with `Async` the downloads happen concurrently and only the Javascript execution is treat synchronously 

![[95397297-b4c85f80-08b7-11eb-8a63-068446b52032.png]]

`Async` will allow the javascript to also run after the document `onReady()` event maybe this is not what you want. `Async` will also vary when it is run as it can be variable based on network speeds. if order matters this will throw a wrench in the works as it can be executed whenever dependent on the users network conditions.

#### Defer

with defer it will defer javascript execution until all the parsing is done, this way all the content is loaded and prepared before javascript begins to act upon them

![[95397383-e9d4b200-08b7-11eb-9075-2acd110eb0a1.png]]

defer will run your deferred code before the document `onReady()` event. and it will stay in order and run when the page is done being parsed.

To imitate the behavior of `defer` people commonly put their script tags in the end of the `</body>` tag, with the `defer` keyword now though we can put the javascript files back in the `<head>` so they are easier to find but still have the same behavior as leaving them at the bottom.

---

Defer is more reliable as it is ordered and you know when it will run. Async can be useful if you have small files that don't depend on anything that you want to have loaded whenever.

---

```html
// Normal
<script src="file.js"></script>
// Async
<script async src="file.js"></script>
// Defer
<script defer src="file.js"></script>
```


---
Tags: 

Reference:

Related:
- 
