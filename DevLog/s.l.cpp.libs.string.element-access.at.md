---
id: r19s5yecyb7ek8ovprq8bi2
title: At
desc: ''
updated: 1641373928326
created: 1641373928326
---


> C++ also supports C-style access of a string using brackets \[] rather than .at(), as in: someString[0]. However, such C-style access does not provide such error checking. Good practice is to use .at() rather than brackets for accessing a string's characters, due to .at()'s error checking.
>
> \-- zybooks

```cpp
string name = "bryan";
cout << name.at(1) << endl;
//#> r
```
