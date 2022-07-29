

#### Parentheses

```shell
( command1; command2 )             # Command group executed within a subshell
Array=(element1 element2 element3) # Array initialization
result=$(COMMAND)                  # Command substitution, new style
>(COMMAND)                         # Process substitution
<(COMMAND)                         # Process substitution
```

#### Double Parentheses

```shell
(( var = 78 ))            # Integer arithmetic
var=$(( 20 + 5 ))         # Integer arithmetic, with variable assignment
(( var++ ))               # C-style variable increment
(( var-- ))               # C-style variable decrement
(( var0 = var1<98?9:21 )) # C-style ternary operation
```

```shell
((a++))

((meaning = 42))

for ((i=0; i<10; i++))

echo $((a + b + (14 * c)))
```

and they enable you to omit the dollar signs on integer and array variables and include spaces around operators for readability.
