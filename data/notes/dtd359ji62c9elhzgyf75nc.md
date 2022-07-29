

## What is it and what is it good for

Adding lots of little tags can get very cumbersome and error prone in JavaScript, so the less HTML tags we need to write in JavaScript the better.

One way to do this is with the Template tag. The content does not render by default but is accessible by JavaScript for modification, Duplication, and more.

```html
<ul>
  <li>
    <span>Item 1: </span>
    <span>Content 1</span>
  </li>
  <li>
    <span>Item 2: </span>
    <span>Content 2</span>
  </li>
</ul>
```

Want to easily add another `<li>` element to the list? Instead of using JavaScript to write the HTML code we can just use the Template:

```html
<ul>
  <li>
    <span>Item 1: </span>
    <span>Content 1</span>
  </li>
  <li>
    <span>Item 2: </span>
    <span>Content 2</span>
  </li>
</ul>

<template>
  <li>
    <span>Item: </span>
    <span>Content</span>
  </li>
</template>
```

## How to use it

Need be able to grab the elements so we assign some classes and id's

```html
<ul id="list">
  <li>
    <span>Item 1: </span>
    <span>Content 1</span>
  </li>
  <li>
    <span>Item 2: </span>
    <span>Content 2</span>
  </li>
</ul>
<button id="add-item">Add Item</button>

<template id="list-item-template">
  <li>
    <span class="title">Item: </span>
    <span class="content">Content</span>
  </li>
</template>
```

Now to access it

```javascript
const template = document.getElementById('list-item-template')
const list = document.getElementById('list')
const button = document.getElementById('add-item')
let itemCount = list.children.length

button.addEventListener('click', () => {
  const item = template.content.cloneNode(true)
  itemCount++
  item.querySelector('.title').innerText = `Item ${itemCount}: `
  item.querySelector('.content').innerText = `Content ${itemCount}`
  list.append(item)
})
```

---

- Reference:
  - <https://blog.webdevsimplified.com/2020-06/template-tag/>
