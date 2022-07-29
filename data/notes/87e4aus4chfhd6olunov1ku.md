

### substr( index, len )

Returns substring starting at index and having len characters.

```cpp
// userText is "http://google.com"
userText.substr(0, 7)                     // Returns "http://"
userText.substr(13, 4)                    // Returns ".com"
userText.substr(userText.length() - 4, 4) // Last 4: ".com"
```
