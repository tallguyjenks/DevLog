

### Implementation

```cpp
#include <iostream>
using namespace std;

class MyClass {
public:
   MyClass();
   MyClass(const MyClass& origClass); // Copy constructor
   ~MyClass();
   
   // Set member value dataObj
   void SetDataObj(const int setVal) {
      *dataObj = setVal;
   }
   
   // Return member value dataObj
   int GetDataObj() const {
      return *dataObj;
   }
private:
   int* dataObj;// Data member
};

// Default constructor
MyClass::MyClass() {
   cout << "Constructor called." << endl;
   dataObj = new int; // Allocate mem for data
   *dataObj = 0;
   
   return;
}

// Copy constructor
MyClass::MyClass(const MyClass& origClass) {
   cout << "Copy constructor called." << endl;
   dataObj = new int; // Allocate sub-object
   *dataObj = *(origClass.dataObj);
   
   return;
}

// Destructor
MyClass::~MyClass() {
   cout << "Destructor called." << endl;
   delete dataObj;

   return;
}

void SomeFunction(MyClass localObj) {
   // Do something with localObj
   return;
}

int main() {
   MyClass tempClassObj; // Create object of type MyClass
   
   // Set and print data member value
   tempClassObj.SetDataObj(9);
   cout << "Before: " << tempClassObj.GetDataObj() << endl;
   
   // Calls SomeFunction(), tempClassObj is passed by value
   SomeFunction(tempClassObj);
   
   // Print data member value
   cout << "After: " << tempClassObj.GetDataObj() << endl;
   
   return 0;
}
```
