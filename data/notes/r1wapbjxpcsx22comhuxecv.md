

## strcmp()

`strchr(sourceStr, searchChar)`

Returns `NULL` if `searchChar` does not exist in `sourceStr`. (Else, returns address of first occurrence, discussed elsewhere).
`NULL` is defined in the cstring library.

```cpp
// Given:
char orgName[100] = "United Nations"; 
char userText[20] = "UNICEF"; 
char targetText[10];

if (strchr(orgName, 'U') != NULL) { // 'U' exists in orgName?
   ...  // 'U' exists in "United Nations", branch taken
}  
if (strchr(orgName, 'u') != NULL) { // 'u' exists in orgName?
   ...  // 'u' doesn't exist (case matters), branch not taken
}
```
