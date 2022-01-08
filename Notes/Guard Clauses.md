---
tags: 💻️
publish: true
aliases:
  - early returns
cssclass: null
created: 2022-01-07 1722
updated: 2022-01-07 1724
---

# [[Guard Clauses]]

---

The idea behind returning early is that you write functions that return the expected positive result at the end of the function.

The rest of the code, in the function, should trigger the termination as soon as possible in case of divergence with the function’s purpose.

An early return does exactly as its name implies. This is what an early return looks like:

```js
function someFunction() {
    if (!someCondition) {
        return;
    }    
    // Do something
}
```

---

- Tags: 
	- 
- Reference:
	- <https://levelup.gitconnected.com/how-you-can-avoid-using-else-in-your-code-871197a1adbc>
- Related:
	- 
