

### Strings

_Strings make use of the [[C++ Include string|string]] library to represent an array of characters (a word or more) in a single datatype with minimal headache on management and more options and functionality than C-style strings_

```cpp
string firstName = "bryan";
```

If you are reading in^\[[[C++ Basic Input Output|c++-basic-input-output]]] a string value into a variable, any spaces will be considered the termination of the string.

To get the entire input string you need to use `getline()`

```cpp
string firstName;
string lastName;
cout << "Enter first name:" << endl;
getline(cin, firstName); // Gets entire line up to ENTER
cout << "Enter last name:" << endl;
getline(cin, lastName); // Gets entire line up to ENTER
cout << endl;
cout << "Welcome " << firstName << " " << lastName << "!" << endl;
cout << "May I call you " << firstName << "?" << endl;
```

