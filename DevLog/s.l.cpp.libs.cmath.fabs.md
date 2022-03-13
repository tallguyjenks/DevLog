---
id: w9owvhbm0rd2835gbjk2tyj
title: Fabs
desc: ''
updated: 1641373550926
created: 1641373550926
---


## fabs()

```cpp
double bodyTemp = 0.0;

cout << "Enter body temperature in Fahrenheit: ";
cin >> bodyTemp;

if (fabs(bodyTemp - 98.6) < 0.0001) {
  cout << "Temperature is exactly normal." << endl;
} else if (bodyTemp > 98.6) {
  cout << "Temperature is above normal." << endl;
} else {
  cout << "Temperature is below normal." << endl;
}
```
