

### Implementation

```cpp
#include <iostream>
using namespace std;

class MyClass {
public:
   MyClass();
   ~MyClass();
   MyClass& operator=(const MyClass& objToCopy);
   
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

// Destructor
MyClass::~MyClass() {
   cout << "Destructor called." << endl;
   delete dataObj;

   return;
}

MyClass& MyClass::operator=(const MyClass& objToCopy) {
   cout << "Assignment op called." << endl;
   
   if (this != &objToCopy) {           // 1. Don't self-assign
      delete dataObj;                  // 2. Delete old dataObj
      dataObj = new int;               // 3. Allocate new dataObj
      *dataObj = *(objToCopy.dataObj); // 4. Copy dataObj
   }
   
   return *this;
}

int main() {
   MyClass tempClassObj1; // Create object of type MyClass
   MyClass tempClassObj2; // Create object of type MyClass
   
   // Set and print object 1 data member value
   tempClassObj1.SetDataObj(9);
   
   // Copy class object using copy assignment operator
   tempClassObj2 = tempClassObj1;
   
   // Set object 1 data member value
   tempClassObj1.SetDataObj(1);
   
   // Print data values for each object
   cout << "obj1:" << tempClassObj1.GetDataObj() << endl;
   cout << "obj2:" << tempClassObj2.GetDataObj() << endl;
   
   return 0;
}
```
