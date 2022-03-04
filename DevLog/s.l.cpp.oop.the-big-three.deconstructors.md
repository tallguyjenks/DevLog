---
id: j2egwdi2n14yzvbpe9nk8yw
title: Deconstructors
desc: ''
updated: 1641372793066
created: 1641372793066
---


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
