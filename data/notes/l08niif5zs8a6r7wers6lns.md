

### The 'New' Operator

> Sometimes memory should be allocated while a program is running and should persist independently of any particular function. The **new** operator allocates memory for the given type and returns a pointer (i.e., the address) to that allocated memory.

```cpp

#include <iostream>
using namespace std;

int main() {
   int* myPtr = nullptr;
   cout << "myPtr: "  << myPtr << endl;
   
   // Next line would cause error because myPtr is null
   // cout << "*myPtr: " << *myPtr << endl; // ERROR
   
   // new allocates int, returns pointer
   myPtr = new int; 
   cout << "myPtr: "  << myPtr << endl;
   cout << "*myPtr: " << *myPtr << endl;
   
   *myPtr = 555;
   cout << "*myPtr: " << *myPtr << endl;
   
   return 0;
}
```

> The new operator is commonly used with class types, as in `new SimpleItem;` where `SimpleItem` is a class name. After new allocates memory for a class object, the object's constructor is called. Arguments may be provided after the class name to call a non-default constructor.

```cpp
#include <iostream>
using namespace std;

class SimpleItem {
public:
   void PrintNums();
   SimpleItem(int initVa1 = -1, int initVal2 = -1);
private:
   int num1;
   int num2;
};

SimpleItem::SimpleItem(int initVal1, int initVal2) {
   num1 = initVal1;
   num2 = initVal2;

   return;
}

void SimpleItem::PrintNums() {
   cout << "num1: " << num1 << endl;
   cout << "num2: " << num2 << endl;

   return;
}

int main() {
   SimpleItem* myItemPtr1 = nullptr;
   SimpleItem* myItemPtr2 = nullptr;
   
   myItemPtr1 = new SimpleItem;
   (*myItemPtr1).PrintNums();
   cout << endl;
   
   myItemPtr2 = new SimpleItem(8, 9);
   (*myItemPtr2).PrintNums();
   
   return 0;
}
```
