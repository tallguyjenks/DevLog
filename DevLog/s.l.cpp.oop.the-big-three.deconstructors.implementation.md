---
id: vul9rcx9eye9tainbc99z2x
title: Implementation
desc: ''
updated: 1641372813765
created: 1641372808225
---


### Implementation

```cpp
#include <iostream>
using namespace std;

class MyClass {
   public:
      MyClass();
      ~MyClass();
   private:
      int* subObj;
};

MyClass::MyClass() {
   cout << "Constructor called." << endl;
   subObj = new int; // Allocate mem for data
   *subObj = 0;
   return;
}

MyClass::~MyClass() {
   cout << "Destructor called." << endl;
   delete subObj;
   return;
}

int main() {
   MyClass* tempClassObj;      // Create object of type MyClass

   tempClassObj = new MyClass; // Allocate mem for object
   delete tempClassObj;        // No more memory leak
                               // Freed obj's mem, including subObj
   // Rest of program ...
   return 0;
}
```
