

## Pointers in C++

> A **pointer** is a variable that contains a memory address, rather than containing data like most variables

## Example

```cpp
#include <iostream>
using namespace std;

int main() {
   int usrInt = 0; // User defined int value
   int* myPtr = nullptr; // Pointer to the user defined int value
   
   // Prompt user for input
   cout << "Enter any number: ";
   cin >> usrInt;
   
   // Output int value and address
   cout << "We wrote your number into variable usrInt." << endl;
   cout << "The content of usrInt is: " << usrInt << "." << endl;
   cout << "usrInt's memory address is: " << &usrInt << "." << endl;
   cout << endl << "We can store that address into pointer variable myPtr."
        << endl;
   
   // Grab address storing user value
   myPtr = &usrInt;
   
   // Output pointer value and value at pointer address
   cout << "The content of myPtr is: " << myPtr << "." << endl;
   cout << "The content of what myPtr points to is: "
        << *myPtr << "." << endl;
   
   return 0;
}
```
