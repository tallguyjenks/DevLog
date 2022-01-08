---
tags: 💻️/Lisp 
publish: true
aliases:
  - 
cssclass: 
created: 2022-01-07 1711
updated: 2022-01-07 1712
---

# [[Lisp Data Types & Structs]]

---

- Type checking

```lisp
(typep foo 'string)
;; NIL
(typep foo 'integer)
;; T
```
		
- The `'` is just short hand for: `(typep foo (quote string))`
	- the `quote` escapes the data to be literal text like:

```lisp
(quote (+ 1 2))
;; (+ 1 2)

'(+ 1 2)
;; (+ 1 2)
```

---

- Tags: 
	- 
- Reference:
	- 
- Related:
	- 
