

##### Pass By References with Const

In [[s.l.cpp.funcs#Pass By References]] the `inputVector` was passed by reference which means any changes made to the vector inside the function body would result in mutation of the original vector as we referred to the original vector.

To prevent mutation of the original vector but take advantage of a pass by reference for efficiency we can prepend `const` to our input parameter so that we wont accidentally be able to mutate that pass by reference value.

```cpp
void MyFunction( const vector<int>& inputVector ) {
	// References my vector but doesnt copy it into the function
	// body scope taking up an identical amount of memory.
	cout << inputVector.at(16345) << endl;
}

int main() {
	vector<int> myVector(785746353);
	
	MyFunction(myVector);
}
```
