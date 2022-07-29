

#### Default Parameters

> Sometimes a function's last parameter (or last few) should be optional. A function call could then omit the last argument, and instead the program would use a default value for that parameter. A function can have a **default parameter value** for the last parameter(s), meaning a call can optionally omit a corresponding argument.

```cpp
#include <iostream>
using namespace std;

// Function prints date in two styles (0: American (default), 1: European)
void DatePrint(int currDay, int currMonth, int currYear, int printStyle = 0) {

   if (printStyle == 0) {      // American
      cout << currMonth << "/" << currDay << "/" << currYear;
   }
   else if (printStyle == 1) { // European
      cout << currDay << "/" << currMonth << "/" << currYear;
   }
   else {
      cout << "(invalid style)";
   }
   
   return;
}

int main() {
   
   // Print dates given various style settings
   DatePrint(30, 7, 2012, 0);
   cout << endl;
   
   DatePrint(30, 7, 2012, 1);
   cout << endl;
   
   DatePrint(30, 7, 2012); // Uses default value for printStyle
   cout << endl;
   
   return 0;
}
```
