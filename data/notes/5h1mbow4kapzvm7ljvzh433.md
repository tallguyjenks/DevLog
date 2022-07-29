

## Copy Assignment Operator

> The problem is that the assignment of `classObj2 = classObj1;` merely copied the pointer for `dataObj`, resulting in `classObj1's dataObj` and `classObj2's dataObj` members both pointing to the same memory location. Printing `classObj2` prints 9 but for the wrong reason, and if `classObj1's dataObj` value was later changed, `classObj2's dataObj` value would seemingly magically change too. Additionally, destroying `classObj1` frees that `dataObj's` memory; destroying `classObj2` then tries to free that same memory, causing a program crash. Furthermore, a memory leak has occurred because neither `dataObj` is pointing at location 81.
> .
> The solution is to overload the "`=`" operator by defining a new function, known as the `copy assignment operator` or sometimes just the `assignment operator`, that copies one class object to another. Such a function is typically defined as:

```cpp
class MyClass {
   public:
      ...
      MyClass& operator=(const MyClass& objToCopy);
      ...
};
```
