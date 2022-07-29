

### Return Statement

A function can only return one item, no more. The return statement is what value you want the function to return to you.

If your function [[s.l.cpp.funcs#Return type]] is `void` then you are returning nothing and you will just use the keyword by itself: `return;`

```cpp
int Square ( int num1, int num2 ) {
	return num1 * num2;
}

int main() {
	int myNum = 7;
	
	std::cout << Square(myNum) << std::endl;
}

//#> 49
```
