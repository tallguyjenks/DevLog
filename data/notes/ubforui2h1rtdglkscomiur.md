

## Constructor Member Initialization

```cpp
// Given

class SampleClass {
   public:
      SampleClass();
      void Print() const;

   private:
      int field1;
      int field2;
};

// Instead of this:

SampleClass::SampleClass() {
   field1 = 100;
   field2 = 200;

   return;
}

// You can do this:

SampleClass::SampleClass() : field1(100), field2(200) {
   return;
}
```

This is not particularly useful for members of basic types, but for data members like [[C++ Arrays and Vectors|vectors]] that need to be explicitly constructed with a size, this can be very useful:

```cpp
class SampleClass {
   public:
      SampleClass();
      void Print() const;

   private:
      vector<int> itemList; 
      // vector<int> itemList(2);  not allowed
};

SampleClass::SampleClass() : itemList(2) {
   // itemList gets constructed with size 2
   return;
}
```
