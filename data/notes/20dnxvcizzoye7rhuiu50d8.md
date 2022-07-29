

### Defer

with defer it will defer javascript execution until all the parsing is done, this way all the content is loaded and prepared before javascript begins to act upon them

![[95397383-e9d4b200-08b7-11eb-9075-2acd110eb0a1.png)

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
