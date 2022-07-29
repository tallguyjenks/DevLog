

## Operator Overloading

Related:

- [[s.l.cpp.polymorphism]]

If you have 2 integers and you add them with `+` then you used the `+` operator. If you want to add 2 private data members that are part of a class that are comprised of multiple parts, the `+` operator is not able to handle this unless we overload it:

```cpp
TimeHrMn time1(3, 22);
TimeHrMn time2(2, 50);
TimeHrMn timeTot;

timeTot = time1 + time2;
timeTot.Print();

//#> H:5, M:72
```

> The + operator was somehow redefined to add TimeHrMn objects' hours and minutes fields separately (3 + 2 is 5, 22 + 50 is 72), leading to simple readable code.
> .
> Although `+` requires left and right operands as in `time1 + time2`, the member function only requires the <u>right operand</u> (rhs: right-hand-side) as the parameter, <u>because the left operand is the calling object</u>. In other words, `time1 + time2` is equivalent to the function call `time1.operator+(time2)`, which is valid syntax but almost never used.

```cpp

#include <iostream>
using namespace std;

class TimeHrMn {
public:
   TimeHrMn(int timeHours = 0, int timeMinutes = 0);
   void Print() const;
   TimeHrMn operator+(TimeHrMn rhs) ; // Overloaded `+` operator
private:
   int hours;
   int minutes;
};

// Overload + operator for TimeHrMn
TimeHrMn TimeHrMn::operator+(TimeHrMn rhs) { // Definition of overload
   TimeHrMn timeTotal;
   
   timeTotal.hours   = hours   + rhs.hours;
   timeTotal.minutes = minutes + rhs.minutes;
   
   return timeTotal;
}

TimeHrMn::TimeHrMn(int timeHours, int timeMinutes) {
   hours  = timeHours;
   minutes = timeMinutes;
   
   return;
}

void TimeHrMn::Print() const {
   cout << "H:" << hours << ", " << "M:" << minutes << endl;
   
   return;
}

int main() {
   TimeHrMn time1(3, 22);
   TimeHrMn time2(2, 50);
   TimeHrMn timeTot;
   
   timeTot = time1 + time2; // Implementation of overloaded operator
   timeTot.Print();
   
   return 0;
}
```

> When an operator like `+` has been overloaded, the compiler determines which `+` operation to invoke based on the operand types. In `4 + 9`, the compiler sees two integer operands and thus applies the built-in `+` operation. In `time1 + time2`, where `time1` and `time2` are `TimeHrMn` objects, the compiler sees two `TimeHrMn` operands and thus invokes the programmer-defined function.
> .
> A programmer can define several functions that overload the same operator, as long as each involves different types so that the compiler can determine which to invoke.

```cpp
#include <iostream>
using namespace std;

class TimeHrMn {
public:
   TimeHrMn(int timeHours = 0, int timeMinutes = 0);
   void Print() const;
   TimeHrMn operator+(TimeHrMn rhs);
   TimeHrMn operator+(int rhsHours);
private:
   int hours;
   int minutes;
};

// Operands: TimeHrMn, TimeHrMn. Call this "A"
TimeHrMn TimeHrMn::operator+(TimeHrMn rhs) {
   TimeHrMn timeTotal;
   
   timeTotal.hours   = hours   + rhs.hours;
   timeTotal.minutes = minutes + rhs.minutes;
   
   return timeTotal;
}

// Operands: TimeHrMn, int. Call this "B"
TimeHrMn TimeHrMn::operator+(int rhsHours) {
   TimeHrMn timeTotal;
   
   timeTotal.hours = hours + rhsHours;
   timeTotal.minutes = minutes; // Stays same
   
   return timeTotal;
}

TimeHrMn::TimeHrMn(int timeHours, int timeMinutes) {
   hours  = timeHours;
   minutes = timeMinutes;
   
   return;
}

void TimeHrMn::Print() const {
   cout << "H:" << hours << ", " << "M:" << minutes << endl;
   
   return;
}

int main() {
   TimeHrMn time1(3, 22);
   TimeHrMn time2(2, 50);
   TimeHrMn timeTot;
   int num = 91;
   
   timeTot = time1 + time2; // Invokes "A"
   timeTot.Print();
   
   timeTot = time1 + 10;    // Invokes "B"
   timeTot.Print();
   
   cout << num + 8 << endl; // Invokes built-in add
   
   // timeTot = 10 + time1; // ERROR: No (int, TimeHrMn)
   
   return 0;
}
```
