---
id: pe3o1k8e6ilynaze0a8zvdf
title: Resize
desc: ''
updated: 1641376720874
created: 1641376720874
---


### resize( num )

Resize string to have num characters. 
If decrease, drops extra chars. 
If increase, sets new chars to null ('\\0', ASCII value 0).

```cpp
// userText is "Help me!"
userText.resize(4); // Now "Help" 
userText.size();    // Returns 4
```
