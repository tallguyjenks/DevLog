---
id: jk4x2030paxwg37woqgh3s8
title: Strchr
desc: ''
updated: 1641373764592
created: 1641373764592
---


## strchr()

`size_t strlen(sourceStr)`

Returns number of characters in `sourceStr` up to, but not including, first null character. `size_t` is integer type.

```cpp
// Given:
char orgName[100] = "United Nations"; 
char userText[20] = "UNICEF"; 
char targetText[10];

x = strlen(orgName);    // Assigns 14 to x 
x = strlen(userText);   // Assigns 6 to x
x = strlen(targetText); // Error: targetText may lack null char
```
