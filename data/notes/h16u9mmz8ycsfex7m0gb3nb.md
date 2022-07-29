

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
