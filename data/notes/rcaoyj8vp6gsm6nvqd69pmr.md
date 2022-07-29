

## Deconstructors

> A destructor has no parameters and no return value (_not even void_)

Just like [[s.l.cpp.oop.the-big-three#Constructors]] Deconstructors share the same name as the class  albeit prepended with a tilde `~` so this is a class with its constructor and destructor:

```cpp
class SampleClass {
   public:
      SampleClass(); // Constructor
      ~SampleClass(); // Destructor
   private:
};
```
