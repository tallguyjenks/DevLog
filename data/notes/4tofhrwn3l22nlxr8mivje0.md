

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
