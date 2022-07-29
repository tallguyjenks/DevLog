

### [[s.l.javascript.releases.ecmascript-2020]]

#### Hot loading modules

```js
const baseModulePath = "./modules";
const btnBooks = document.getElementById("btnBooks");
let bookList = [];

btnBooks.addEventListener("click", async e => {
  const bookModule = await import(`${baseModulePath}/books.js`);

  bookList = bookModule.loadList();
});
```

So this code will only load the module on a particular click event, instead of a static declaration at the top of a file.
