---
id: xlJ8qK8E8w99sOYKo2UjE
title: Constructors
desc: ''
updated: 1641372180335
created: 1641105063887
stub: false
isDir: false
---

Constructors initialize instances of a class. A best practice is to initialize all variables when declared (likely to keep them in the same memory location on the stack). 

Constructors share the same name as the class name:

```cpp
#include <iostream>
#include <string>
using namespace std;

/*** ShopItem class definition ***/
class ShopItem {
public:
   void SetNameAndPrice(string itemName, int itemPrice);
   void Print() const;
   ShopItem();  // Default constructor
   
private:
   string name;  // Ex: "Bag of salad"
   int    price; // Price in cents. Ex: 199
};

ShopItem::ShopItem() {  // Default constructor
   name  = "NoName";    // Default name
   price = -1;          // Default price
   
   return;
}

void ShopItem::SetNameAndPrice(string itemName, int itemPrice) {
   name  = itemName;
   price = itemPrice;
   
   return;
}

void ShopItem::Print() const {
   cout << "Name: "  << name  << ", ";
   cout << "Price: " << price << endl;
   
   return;
}

/*** End definitions for ShopItem class ***/

int main() {
   ShopItem item1;  // Auto-calls default constructor
   
   item1.Print();
   
   item1.SetNameAndPrice("Soap", 385);
   item1.Print();
   
   return 0;
}
```
