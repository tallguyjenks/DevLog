

#### pop_back()

Just like `pop()` in Javascript, this removes the last element from the vector. 

```cpp
// playersList is 55, 99, 44 (size 3)

playersList.pop_back();     // Removes last element

// playersList now 55, 99    (size 2)

cout << playersList.back(); // Common combination of back() 

playersList.pop_back();     // followed by pop_back()

// Prints 99. playersList becomes just 55

cout << playersList.pop_back(); // Common error 
                                // pop_back() returns void
```
