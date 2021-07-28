---
tags: 
aliases: 
  - ⟨template⟩
cssclass: 
---

#### [[HTML Template Tag]]

---

# What is it and what is it good for

Adding lots of little tags can get very cumbersome and error prone in JavaScript, so the less HTML tags we need to write in JavaScript the better.

One way to do this is with the [[HTML Template Tag|⟨template⟩]] tag. The content does not render by default but is accessible by JavaScript for modification, Duplication, and more.

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

Want to easily add another `<li>` element to the list? Instead of using JavaScript to write the HTML code we can just use the [[HTML Template Tag|⟨template⟩]]:

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

# How to use it

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

[[JavaScript The CONST Keyword|const]] template = [[JavaScript DOM Manipulation|document]][[JavaScript getElementById Method|.getElementById(]]'list-item-template'[[JavaScript getElementById Method|)]]
[[JavaScript The CONST Keyword|const]] list = [[JavaScript DOM Manipulation|document]][[JavaScript getElementById Method|.getElementById(]]'list'[[JavaScript getElementById Method|)]]
[[JavaScript The CONST Keyword|const]] button = [[JavaScript DOM Manipulation|document]][[JavaScript getElementById Method|.getElementById(]]'add-item'[[JavaScript getElementById Method|)]]
[[JavaScript The Let Keyword|let]] itemCount = list #✅️/🟨️ 

button[[JavaScript Event Listeners#Click event|.addEventListener('click',]] [[JavaScript Arrow Functions|() => {]]

[[JavaScript The CONST Keyword|const]] item = template[[JavaScript Template Cloning|.content.cloneNode(true)]]
itemCount++
item[[JavaScript querySelector Method|.querySelector(]]'.title'[[JavaScript querySelector Method|)]][[JavaScript innerText Method|.innerText]] = #✅️/🟨️ 
item[[JavaScript querySelector Method|.querySelector(]]'.content'[[JavaScript querySelector Method|)]][[JavaScript innerText Method|.innerText]] = #✅️/🟨️ 
list #✅️/🟨️ 

[[JavaScript Arrow Functions|})]]

---
Tags: 

Reference:
- <https://blog.webdevsimplified.com/2020-06/template-tag/>

Related:
