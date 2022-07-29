

Footnotes are declared with a single pair of square brackets prepended with a carat: `^[]`

Footnotes are like similar to [[Markdown Links|s.m.markdown.syntax.links]] with the separation of declaration and definition.

if i declare a footnote`[^1]`

Then the definition can be defined later:

`[^1]: the definition`

What is really helpful is an all in one solution with inline footnotes`^[Through leaving the footnote text in the brackets like this]`

if you have a large block in the footnote definition you can indent sub-levels to make it all part of the same content block:

```
block[^1]

[^1]: this is a text link
	indented block
```

block[^1]

[^1]: this is a text link
    indented block

In obsidian inside of inline footnotes you can also insert the wiki links in the footnotes themselves`^[[[Like this]]]`	
