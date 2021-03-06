---
id: 31nnsx6afp48kj8yh318w57
title: Funcs
desc: ''
updated: 1641429117387
created: 1641429117387
---


#### Functions In Bash

- [[s.l.bash.vars]] assigned outside of functions can be overwritten in functions and display aberrant results if local isn't used.

```bash
foo="bar"
echo "top level: $foo"

main(){
	foo="func bar"
	echo "func $foo"
}
main
echo "end $foo"

# OUTPUT:
#> top level: bar
#> func func bar
#> end func bar

#===#===#===#===#===#===#

foo="bar"
echo "top level: $foo"

main(){
	local foo="func bar"
	echo "func $foo"
}
main
echo "end $foo"

# OUTPUT:
#> top level: bar
#> func func bar
#> end bar
```

- Do not use the function keyword, it reduces compatibility with older versions of bash.

```bash
# Right.
do_something() {
	# ...
}

# Wrong.
function do_something() {
	# ...
}
```

```bash
# Current function.
"${FUNCNAME[0]}"

# Parent function.
"${FUNCNAME[1]}"

# So on and so forth.
"${FUNCNAME[2]}"
"${FUNCNAME[3]}"

# All functions including parents.
"${FUNCNAME[@]}"
```
