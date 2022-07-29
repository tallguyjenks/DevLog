

### Output

`ofstream` = Output File Stream

```cpp
#include <iostream>
#include <fstream>
using namespace std;

int main() {
   ofstream outFS; // Output file stream
   
   // Open file
   outFS.open("myoutfile.txt");
   
   if (!outFS.is_open()) {
      cout << "Could not open file myoutfile.txt." << endl;
      return 1;
   }
   
   // Write to file
   outFS << "Hello" << endl;
   outFS << "1 2 3" << endl;
   
   // Done with file, so close it
   outFS.close();
   
   return 0;
}
```
