

### find( item, index )

Starts at a 0 index and returns index position of your input. Optional 2nd argument can tell you which index to start at so as to skip the first occurrence of something.

```cpp
// userText is "Help me!"
userText.find('p')    // Returns 3 
userText.find('e')    // Returns 1 (first occurrence of e only) 
userText.find('z')    // Returns string::npos 
userText.find("me")   // Returns 5
userText.find('e', 2) // Returns 6 (starts at index 2)
```
