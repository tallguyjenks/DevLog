

## Class Copy Constructors

If a class has a constructor that allocates memory for a variable with a pointer:

```cpp
class MyClass {
public:
   MyClass();
   ~MyClass();
   
   // Set member value dataObj
   void SetDataObj(const int setVal) {
      *dataObj = setVal;
   }
   
   // Return member value dataObj
   int GetDataObj() const {
      return *dataObj;
   }
private:
   int* dataObj;// Data member
};
```

And a new class is instantiated, and then passed by **value** to a function:

```cpp
void SomeFunction(MyClass localObj) {
   // Do something with localObj
}

int main() {
   MyClass tempClassObj; // Create object of type MyClass
   
   // Set and print data member value
   tempClassObj.SetDataObj(9);
   cout << "Before: " << tempClassObj.GetDataObj() << endl;
   
   // Calls SomeFunction(), tempClassObj is passed by value
   SomeFunction(tempClassObj);
   
   // Print data member value
   cout << "After: " << tempClassObj.GetDataObj() << endl; // ERROR
   
   return 0;
}

```

You get an error because the pass by value acts as a member wise copy.:

- newA = oldA
- newB = oldB

If your class doesn't have pointers then you wont have this issue. But with pointers we need to take a special approach. We need a copy constructor so that when passed by value to a function, when the class is copied locally we don't mess with the pointers. This copy constructor creates a new copy of the original class called a **deep copy**. 

> The **copy constructor** can be called with a single pass by reference argument of the class type, representing an original object to be copied to the newly-created object:

```cpp
class MyClass {
   public:
      ...
      MyClass(const MyClass& origClass);
      ...
};
```

```cpp
/*
	A class's copy constructor will be called automatically when an object of the class type 
	is passed by value to a function, and also when an object is initialized by copying another 
	object during declaration, as in: 
*/
MyClass classObj2 = classObj1; 
// or 
obj2Ptr = new MyClass(classObj1);.
```
