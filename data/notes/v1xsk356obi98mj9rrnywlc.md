

## Syntax

Markdown links are created with a pair of square brackets and the URL in the parens: `[Bryans Website](https://www.bryanjenks.dev)`

Explicit links without alternatively displayed text you can paste them directly or within angle brackets:

`https://www.bryanjenks.dev`

or

`<https://www.bryanjenks.dev>`

Links can also link to markdown headings in the same document like a table of contents: spaced must be replaced with dashes but have to begin with a hash:

`[Headings](#Syntax)`

[go to test](#test)

Link text can also be subject to [[Markdown Font Formatting|s.m.markdown.syntax.font-formatting]]

such as `**[a bold link](https://www.bryanjenks.dev)**`

These are not [[Markdown Footnotes|s.m.markdown.extended-functionality.footnotes]] however they function somewhat similarly. you link to a specific identifier, word/number with the definition later defined:

`[test][1]`

```
`[1]: https://www.bryanjenks.dev`
```

spaces in markdown links need to be represented with `%20` 
