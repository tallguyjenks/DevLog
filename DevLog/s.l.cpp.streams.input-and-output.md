---
id: 14c3zf0208ip3f2f0693qwi
title: Input and Output
desc: ''
updated: 1641377557341
created: 1641377557341
---


### Input / Output

#### Output Stream

or `ostream` for short is a class that supports output. It is included from [[s.l.cpp.libs.iostream]]

`<iostream>` provides the `<<` operator known as the **insertion operator**.

`cout` is a predefined `ostream` object (e.g., you can think of it as declared as `ostream cout;`

> The `<<` operator is overloaded with functions to support the various standard data types, such as int, bool, float, etc., each function converting that data type to a sequence of characters. The operator may be further overloaded by the string library from `#include <string>` or by the programmer for programmer-created classes.
> .
> The `<<` operator returns a reference to the `ostream` that called it, and is evaluated from left to right like most operators, so `<<` operators can appear in series.

```cpp
cout << "Num" << myInt;

// can be thought of as:

( cout.operator<<("Num") ).operator<<(myInt);
```

#### Input Stream

Or `istream`, provides the `>>` operator known as the **extraction operator**. To extract data from a data buffer and write the data into different types of variables.

> `cin` is a predefined istream pre-associated with a system's standard input, usually a computer keyboard. The system automatically puts the standard input into a data buffer associated with `cin`. The `>>` operator <u>skips leading whitespace</u>, extracts as many characters as possible consistent with the target variable's type and <u>stopping at the next whitespace</u>, converts the extracted characters to the target variable's type, and stores the result into the variable.
