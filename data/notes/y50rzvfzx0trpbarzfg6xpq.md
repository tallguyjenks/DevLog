

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
