---
id: zoy7hd76iedni9yleun1nxm
title: Constructor Overloading
desc: ''
updated: 1641372147328
created: 1641372147328
---


## Constructor Overloading

Just like with  [[C++ Polymorphism|c++-polymorphism#Function Name Overloading]] you can overload a constructor to instantiate the same object (class) with different initialization values based on the parameters passed to the constructor:

```cpp
class Seat {
   public:
      ...
   Seat(); // Default constructor
   Seat(string resfirstName, string resLastName, int resAmountPaid); // Second constructor
      ...
};

Seat::Seat() { // Default constructor
   firstName  = "none";
   lastName   = "none";
   amountPaid = -1;
}

Seat::Seat(string resfirstName, string resLastName, int resAmountPaid) { // Second constructor
   firstName  = resfirstName;
   lastName   = resLastName;
   amountPaid = resAmountPaid;
}
```
