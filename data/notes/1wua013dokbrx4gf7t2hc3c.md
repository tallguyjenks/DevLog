

### Return type

Before each function [[s.l.cpp.funcs#Declaration]] you must have a return type for that function. The return type is the data type for what is returned by the function. Most of the data types you will use are in [[C++ Variables and Datatypes|c++-variables-and-datatypes]] but one you will also use is `void` this is when the function will return nothing to you, but it may perform actions such as mutate data, or log things to the console, but no value is returned.

```cpp
void SayHello() {
	std::cout << "hello world!" << std::endl;
}

int main() {
	SayHello();
}

//#> "hello world!"
```
