

### Parameters

Parameters passed to a function need to have their data types explicitly declared as well so the function knows what type of data it is receiving:

```cpp
#include <string>

void SayHello ( string name, int age ) {
	std::cout << "Hello " << name 
	<< " you are: " << age << " years old!" << std::endl;	
}

int main () {
	string myName = "Bryan";
	int myAge = 28;
	
	SayHello( myName, myAge );
}

//#> "Hello Bryan you are: 28 years old!"
```


