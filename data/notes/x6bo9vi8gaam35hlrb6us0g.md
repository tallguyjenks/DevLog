

## Efficient Usage

The most classic form of the if-else statement looks really simple.

```js
if (someCondition) {
   // 10 lines of code
} else {
   // More code..
}
```

This is how we could use a return in order to get rid of the else block:

```js
if (someCondition) {
   // 10 lines of code
   return;
} 
// More code..
```

If-else statements get used a lot to assign variables

```js
if (someCondition) {
   number = someNumber * 2
} else {
   number = 1
}
```

When you spot code like this, change it. The way to get rid of the else block is by assigning a default value.

```js
number = 1
if (someCondition) {
   number = someNumber * 2
}
```

There’s a way to optimize this code even more. We could make this piece of code a one-liner by using the conditional operator:

```js
number = someCondition ? someNumber * 2 : 1;
```

[[theory.guard-clauses]] are also known as early-returns.

![[theory.guard-clauses]]

---

- Reference:
  - <https://levelup.gitconnected.com/how-you-can-avoid-using-else-in-your-code-871197a1adbc> 
