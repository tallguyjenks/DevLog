

#### Brackets

<http://wiki.bash-hackers.org/scripting/obsolete>

```shell
if [ CONDITION ]    # Test construct
if [[ CONDITION ]]  # Extended test construct
Array[1]=element1   # Array initialization
[a-z]               # Range of characters within a Regular Expression
$[ expression ]     # A non-standard & obsolete version of $(( expression )) 
```

Single brackets are also used for array indices:

```shell
array[4]="hello"

element=${array[index]}
```
