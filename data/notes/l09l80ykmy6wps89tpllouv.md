

### Variables

Variables in bash are assigned with a single `=`
No spacing between the variable name, the `=` and the assigned value
You can specify the variables scope with either `export` or `local` or
an environmental variable with no explicit scope.

Once declared in your script or environment etc, you can reference your
variables by matching the exact casing of the variable name and pre-pending
a `$` so my path variable for binaries to execute would be `$PATH`.

When referencing your variables always quote them because of:
"General rule: quote it if it can either be empty or contain spaces"
"`$?` doesn't need quotes since it's a numeric value."

```shell
## Variables

### Local vars
local var=2

### Global Vars
var=2

### Environment
export var=2

echo "$var"
```

"In short, quote everything where you do not require the shell to perform token
splitting and wild card expansion."

```shell

## Token Splitting
words="foo bar baz"
for word in $words; do
  echo "$word"
done
#> foo
#> bar
#> baz

```

Double quotes are suitable when variable interpolation is
required. With suitable adaptations, it is also a good workaround when you need
single quotes in the string. (There is no straightforward way to escape a
single quote between single quotes, because there is no escape mechanism inside
single quotes -- if there was, they would not quote completely verbatim.)

No quotes are suitable when you specifically require the shell to perform token
splitting and/or wild card expansion.

```shell
## Wildcard Expansion

### Literal Strings
pattern='file*.txt'
ls $pattern
# > file1.txt      file_other.txt

### Double Quotes
ls "$pattern"
#> ls: cannot access file*.txt: No such file or directory
# (There is no file named literally file*.txt.)

ls '$pattern'
#> ls: cannot access $pattern: No such file or directory
# (There is no file named $pattern, either!)
```

In more concrete terms, anything containing a filename should usually be quoted
(because filenames can contain whitespace and other shell meta characters).
Anything containing a URL should usually be quoted (because many URL's contain
shell meta characters like `?` and `&`). Anything containing a regex should usually
be quoted (ditto ditto). Anything containing significant whitespace other than
single spaces between non-whitespace characters needs to be quoted (because
otherwise, the shell will munge the whitespace into, effectively, single
spaces, and trim any leading or trailing whitespace).

When you know that a variable can only contain a value which contains no shell
meta characters, quoting is optional. Thus, an unquoted `$?` is basically fine,
because this variable can only ever contain a single number. However, `"$?"` is
also correct, and recommended for general consistency and correctness (though
this is my personal recommendation, not a widely recognized policy).

Values which are not variables basically follow the same rules, though you
could then also escape any meta characters instead of quoting them. For a common
example, a URL with a & in it will be parsed by the shell as a background
command unless the meta character is escaped or quoted.



#### Meta characters with variables

The braces, in addition to delimiting a variable name are used for parameter expansion so you can do things like:

Truncate the contents of a variable

```shell
var="abcde"; echo ${var%d*}
#> abc
```

Make substitutions similar to sed

```shell
var="abcde"; echo ${var/de/12}
#> abc12
```

Use a default value

```shell
default="hello"; unset var; echo ${var:-$default}
#> hello
```

and several more

Also, brace expansions create lists of strings which are typically iterated over in loops:

```shell
echo f{oo,ee,a}d
#> food feed fad

mv error.log{,.OLD}
# (error.log is renamed to error.log.OLD because the brace expression
# expands to "mv error.log error.log.OLD")

for num in {000..2}; do echo "$num"; done
#> 000
#> 001
#> 002

echo {00..8..2}
#> 00 02 04 06 08

echo {D..T..4}
#> D H L P T
```

#### Exporting variables

Export variables for other programs to use in your shell environment with

```shell
export var=myvar
```

variable with

```shell
unset myvar
```

Export copies variables to the environment, `declare -x` also does the same as export?

Export functions with

```shell
export -f myfunc
```

Just printing export will list all current environment variables

Functions don’t get a copy of the variables in the environment, they share them and therefor can mutate them

To see built-ins use

```shell
enable
```

To see keywords use

```shell
compgen -k
```
