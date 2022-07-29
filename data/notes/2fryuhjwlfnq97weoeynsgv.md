

#### Sub-String Removal In Bash

Removing substrings without `awk`/`cut` function calls

```shell
string="hello-world"
prefix="hell"
suffix="ld"

foo=${string#"$prefix"}
foo=${foo%"$suffix"}
echo "${foo}"
#===#===#===#===#===#===#===#
string="hello-world"
prefix="hell"
suffix="ld"

#remove "hell" from "hello-world" if "hell" is found at the beginning.
prefix_removed_string=${string/#$prefix}

#remove "ld" from "o-world" if "ld" is found at the end.
suffix_removed_String=${prefix_removed_string/%$suffix}
echo $suffix_removed_String
#> o-wor

# NOTES:
# `#$prefix` : adding `#` makes sure that substring "hell" is removed only if
# it is found in beginning.
# `%$suffix` : adding `%` makes sure that substring "ld" is removed only if it
# is found in end.

# Without these, the substrings "hell" and "ld" will get removed everywhere,
# even it is found in the middle.

var="apple orange"
# this command will print 'apple'
echo "${var%% *}"

# This command will print 'orange'
echo "${var##* }"
```


