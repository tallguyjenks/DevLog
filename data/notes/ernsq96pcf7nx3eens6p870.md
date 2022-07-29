

## Using Pointers Example

```cpp
#include <iostream>
using namespace std;

int main() {
   double vehicleMpg = 0.0;
   double* valPtr = nullptr;
   
   valPtr = &vehicleMpg;
   
   *valPtr = 29.6; // Assigns the number to the variable
                   // POINTED TO by valPtr.
   
   // vehicleMpg = 40;   // Uncomment this later
   
   cout << "Vehicle MPG = " << vehicleMpg << endl;
   cout << "Vehicle MPG = " << *valPtr << endl;
   
   return 0;
}
```
