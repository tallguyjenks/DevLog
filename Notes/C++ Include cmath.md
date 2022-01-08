---
tags: 💻️/C++
publish: true
aliases:
  - null
cssclass: null
created: 2022-01-07 1719
updated: 2022-01-07 1720
---

# [[C++ Include cmath]]

---

## The C Math Library

### Other Functions

#### fabs()

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

---

- Tags: 
	- 
- Reference:
	- 
- Related:
	- 
