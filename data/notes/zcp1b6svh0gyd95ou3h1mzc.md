

## Snippets look like this:

```
snippet s "my snippet"
"Hello There"$0
endsnippet
```

## Global Snippets

_This makes The snippet apply the code to all python code blocks used_
_in snippets. This is useful for modular code and defining methods_
_outside of the snippet to be used across many._

_!p for python, !v for Vim script and \`\` for bash_

```
global !p
code...
endglobal
```

Tab stops
mirrors
visual tokens
default text
shell commands
Vim Script commands
python commands
