

#### resize()

To dynamically resize a vector while program is executing and size is not known during compile time.

```cpp
vctr.resize(N);  // Allocates N elements for vector vctr.
```

resize is now adding new slots on top of existing elements, rather it just states that _"THIS is how many elements are in this vector"_. If the resize value is smaller than the vectors current size, all elements in indexes larger than `N` are destroyed and `N` is now the size of the vector.
