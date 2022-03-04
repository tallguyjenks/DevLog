---
id: 25j6ace09d4blyj3j4t3vem
title: Strcopy
desc: ''
updated: 1641373647626
created: 1641373647626
---


## strcpy()

`strcpy(destStr, sourceStr)`

> Copies sourceStr (up to and including null character) to destStr.	

```cpp
strcpy(targetText, userText); // Copies "UNICEF" + null char 
                              // to targetText 
strcpy(targetText, orgName);  // Error: "United Nations" 
                              // has > 10 chars
targetText = orgName;         // Error: Strings can't be 
                              // copied this way
```
