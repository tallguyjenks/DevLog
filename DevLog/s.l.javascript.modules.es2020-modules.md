---
id: 8guqxw2wd7jkml4eu80wq7i
title: Es2020 Modules
desc: ''
updated: 1641407971856
created: 1641407960879
---


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
