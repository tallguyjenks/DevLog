

#### C Strings

char arrays were the only type of strings that existed in `C` such as:

```cpp
char movieTitle[20] = "Star Wars";
```

> Because a string can be shorter than the character array, a string in a char array must end with a special character known as a null character, written as '\\0'. Given a string literal like "Star Wars", the compiler automatically appends a null character.
> .
> A char array of size 20 can store strings of lengths 0 to 19. The longest string is 19, not 20, since the null character must be stored.

`C` strings can be in legacy code and are included with:

```cpp
#include <cstring>
```
