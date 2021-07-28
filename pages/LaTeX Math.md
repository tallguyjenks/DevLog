---
tags:
aliases: 
  - Mathjax
cssclass: 
---

#### [[LaTeX Math]]

---

## Math Environment

to use LaTeX math you need to create a math environment:

```
$MATH GOES HERE$
```

When rendered this will look like: $MATH GOES HERE$

This is an in-line equation

For a multi-line equation that also centers itself you use double dollars

```
$$MATH GOES HERE$$
```

Rendered it will center: $$MATH GOES HERE$$

## Syntax

### Common Constructs

- `x^2` = $x^2$ ^d77d52
- `x_{ij}` = $x_{ij}$ ^8a61f1
- `\sqrt{4}` = $\sqrt{4}$
- `\sqrt[n]{4}` = $\sqrt[n]{4}$ ^cc4666
- `\frac{2}{3}` = $\frac{2}{3}$

### Super and sub script

Super uses a carat `^`

![[#^d77d52]]

Sub-script uses an underscore `_` 

![[#^8a61f1]]

### Grouping Items

using the braces `{ }` we can group items together

![[#^d77d52]]

V.S.

`x_ij` = $x_ij$

Where the `J` is back at the normal level not the subscript level

### Optional Arguments

Some commands take optional arguments in square brackets `[ ]`

![[#^cc4666]]

### Escaped Operators and Characters

things like `\pi` yield $\pi$ they have no braces `{ }` or brackets `[ ]` and instead are just themselves. This means they can be inserted into other commands and the only limitation might be a space after the escaped sequence so that it doesnt turn into something like `\pix` when you wanted $\pi  x$

#### Equations are like sentences

These sequences all together read like a sentence with symbols and syntax determining positioning and what is rendered in a logical format

```
$$\sum_{j=0}^7j^2$$
```

$$\sum_{j=5}^7j^2$$

Reads like "*$\sum$*, then below it add *$J=5$*, raise that whole combo to the power of *$7$* then adjacent to that place *$J^2$*.

### Insertable Symbols

#### Calligraphic letter

`\mathcal{LETTER}` == $\mathcal{LETTER}$

#### Greek

[[Greek Letters In Statistics]]


`$\Sigma\,\Delta$$` == $\Sigma\,\Delta$ 

#### Dots

Vertical dots == *$\vdots$*
Centered dots == *$\cdots$*
Low dots == *$\ldots$*
diagonal dots == *$\ddots$*

using the spacer comma `\,` [[#^50285a]]
*$\{2,3,\,\ldots\}$*

#### Fences

<br><br><br><br>

![[Pasted image 20210110231926.png]]

<br><br>

#### Arrays and Matrices

<br><br><br><br>

![[Pasted image 20210110232016.png]]

<br><br>

$$
\Bigg\{\,\begin{array}{rcl}
	0&6&6 \\
	0&6&6 \\
	0&6&6 \\
\end{array}\,\Bigg\}
$$

#### Spacing

|**LaTeX**|*Code*|
|:-----|:---------|
|$x\,y$ | `$x\,y$`|
|$x\:y$ | `$x\:y$`|
|$x\;y$ | `$x\;y$`|
|$x \quad y$ | `$x \quad y$`|
|$x \qquad y$ | `$x \qquad y$`|
|$x\!y$ | `$x\!y$`|

Sometimes you may want some extra space between elements and a space wont work and you need something like `\,`: ^50285a

`\Sigma \Delta` == $\Sigma \Delta$

v.s.

`\Sigma\,\Delta` == $\Sigma\,\Delta$

There is now a slight space between the two

---
Tags: 

Reference:
[[undergradmath.pdf]]
Related:
- https://castel.dev/post/lecture-notes-1/
- https://arachnoid.com/latex/
