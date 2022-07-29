

### Example

`StoreItem.h`

```cpp
#ifndef STOREITEM_H
#define STOREITEM_H

class StoreItem {
   public:
      void SetWeightOunces(int ounces);
      void Print() const;
   private:
      int weightOunces;
};

#endif
```

`StoreItem.cpp`

```cpp
#include <iostream>
using namespace std;

#include "StoreItem.h"

void StoreItem::SetWeightOunces(int ounces) {
   weightOunces = ounces;
   return;
}

void StoreItem::Print() const {
   cout << "Weight (ounces): " << weightOunces << endl;
   return;
}
```

`main.cpp`

```cpp
#include <iostream>
using namespace std;

#include "StoreItem.h"

int main() {
   StoreItem item1;

   item1.SetWeightOunces(16);
   item1.Print();

   return 0;
}
```
