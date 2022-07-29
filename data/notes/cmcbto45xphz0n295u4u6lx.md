

#### Pass By References

> A **pass by reference** parameter does not create a local copy of the argument, but rather the parameter refers directly to the argument variable's memory location. Appending & to a parameter's data type makes the parameter pass by reference type.

```cpp
void MyFunction( vector<int>& inputVector ) {
	// References my vector but doesnt copy it into the function
	// body scope taking up an identical amount of memory.
	cout << inputVector.at(16345) << endl;
}

int main() {
	vector<int> myVector(785746353);
	
	MyFunction(myVector);
}
```


