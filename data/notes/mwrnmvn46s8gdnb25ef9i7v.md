

### Internal Field Separator - IFS

`IFS` = Internal Field Separator.

Unbelievable as it may seem, [[POSIX|posix]] requires the treatment of IFS as a field terminator, rather than a field separator. What this means in our example is that if there's an empty field at the end of the input line, it will be discarded:

```shell

IFS=, read -ra fields <<< "a,b,"
declare -p fields
#> declare -a fields='([0]="a" [1]="b")'

```

Where did the empty field go? It was eaten for historical reasons ("because it's always been that way"). This behavior is not unique to bash; all conforming shells do it. A non-empty field is properly scanned:

```shell

IFS=, read -ra fields <<< "a,b,c"
declare -p fields
#> declare -a fields='([0]="a" [1]="b" [2]="c")'

```

So, how do we work around this nonsense? As it turns out, appending an `IFS` character to the end of the input string will force the scanning to work. If there was a trailing empty field, the extra `IFS` character "terminates" it so that it gets scanned. If there was a trailing non-empty field, the `IFS` &lt;character creates a new, empty field that gets dropped.

```shell

input="a,b,"
IFS=, read -ra fields <<< "$input,"
declare -p fields
#> declare -a fields='([0]="a" [1]="b" [2]="")'

```

<https://mywiki.wooledge.org/BashPitfalls>
<https://mywiki.wooledge.org/IFS>
