

## strlen()

`int strcmp(str1, str2)`

Returns 0 if `str1` and `str2` are equal, non-zero if they differ.

```cpp
// Given:
char orgName[100] = "United Nations"; 
char userText[20] = "UNICEF"; 
char targetText[10];

if (strcmp(orgName, "United Nations") == 0) {
   ... // Equal, branch taken
}
if (strcmp(orgName, userText) == 0) {
   ... // Not equal, branch not taken
}
```
