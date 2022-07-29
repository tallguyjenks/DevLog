

### Pointer Variables

> Appending `*` after a data type in a variable declaration declares a pointer variable, as in `int* myPtr`. One might imagine that the programming language would have a type like address in addition to types like int, char, etc., but instead the language requires each pointer variable to indicate the type of data to which the address points. So valid pointer variable declarations are `int* myPtr1`, `char* myPtr2`, `double* myPtr3`, and even `Seat* myPtr4;` (where Seat is a class type); all such variables will contain memory addresses.

```cpp
int* myInt;
```
