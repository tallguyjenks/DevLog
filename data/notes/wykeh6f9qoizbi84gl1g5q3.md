

#### Number Formatting

> A programmer can adjust the way that output appears, a task known as output formatting. The main formatting approach uses manipulators. A manipulator is an item designed to be used with the insertion operator `<<` or extraction operator `>>` to adjust the way output appears, and is available via `#include <iomanip>; `or `#include <ios>;` in namespace std. For example, `cout << setprecision(3) << myFloat;` causes the floating-point variable `myFloat` to be output with only 3 digits; if `myFloat` was 12.34, the output would be 12.3.
> .
> <u>Most manipulators change the state of the stream such that the manipulation affects all subsequent output, not just the next output.</u>

| Manipulator     | Description                                                                                                                                   | Example                                                                            |
| :-------------- | :-------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------- |
| fixed           | Use fixed-point notation. `From <ios>`                                                                                                        | 12.34                                                                              |
| scientific      | Use scientific notation. `From <ios>`                                                                                                         | 12.3E+01                                                                           |
| setprecision(p) | If stream has not been manipulated to fixed or scientific: Sets max number of digits in number                                                | p=3 yields 12.3 p=5 yields 12.34                                                   |
|                 | If stream has been manipulated to fixed or scientific: Sets max number of digits in fraction only (after the decimal point). From `<iomanip>` | fixed: p=1 yields 12.3 scientific: p=1 yields 1.2e+01                              |
| showpoint       | Even if fraction is 0, show decimal point and trailing 0s. Opposite is noshowpoint. `From <ios>`                                              | For 99.0 with precision=2 and fixed: 99 (default or noshowpoint) 99.00 (showpoint) |

```cpp
#include <iostream>
#include <ios>
#include <iomanip>
using namespace std;

int main() {
   
   double milesTrvld = 765.4321;
   
   cout << "setprecision(p) -- Sets # digits" << endl;
   cout << milesTrvld << " (default p is 6)" << endl;
   cout << setprecision(8) << milesTrvld << " (p = 8)" << endl;
   cout << setprecision(5) << milesTrvld << " (p = 5)" << endl;
   cout << setprecision(2) << milesTrvld << " (p = 2)"
        << " (note rounding)" << endl;
   cout << milesTrvld << " (manipulator persists)" << endl << endl;
   
   cout << setprecision(2);
   cout << "(For following, p = 2 applies to fraction only)" << endl;
   
   // fixed -- uses fixed point notation
   cout << fixed;
   cout << "fixed: " << milesTrvld << endl;
   
   // scientific -- uses scientific notation
   cout << scientific;
   cout << "scientific: " << milesTrvld << endl;
   
   return 0;
}
```
