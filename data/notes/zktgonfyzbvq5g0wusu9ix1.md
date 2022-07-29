

### Escaped Operators and Characters

things like `\pi` yield $\pi$ they have no braces `{ }` or brackets `[ ]` and instead are just themselves. This means they can be inserted into other commands and the only limitation might be a space after the escaped sequence so that it doesnt turn into something like `\pix` when you wanted $\pi  x$

#### Equations are like sentences

These sequences all together read like a sentence with symbols and syntax determining positioning and what is rendered in a logical format

```latex
$$\sum_{j=0}^7j^2$$
```

$\sum_{j=5}^7j^2$

Reads like "_$\sum$_, then below it add _$J=5$_, raise that whole combo to the power of _$7$_ then adjacent to that place _$J^2$_.
