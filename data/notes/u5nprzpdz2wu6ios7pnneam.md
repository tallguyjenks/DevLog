

### String Streams

#### Input Stream

> Sometimes a programmer wishes to read input data from a string rather than from the keyboard (standard input). A new input string stream variable of type `istringstream` can be created that is associated with a string rather than with the keyboard (standard input). `istringstream` is derived from `istream`. Such a stream can be used just like the `cin` stream. The following program illustrates.

```cpp
#include <iostream>
#include <sstream>
#include <string>
using namespace std;

int main() {
   string  userInfo = "Amy Smith 19"; // Input string
   istringstream inSS(userInfo);      // Input string stream
   string firstName;                  // First name
   string lastName;                   // Last name
   int userAge = 0;                   // Age
   
   // Parse name and age values from input string
   inSS >> firstName;
   inSS >> lastName;
   inSS >> userAge;
   
   // Output parsed values
   cout << "First name: " << firstName << endl;
   cout << "Last  name: " << lastName << endl;
   cout << "Age: "        << userAge << endl;
   
   return 0;
}

//#> First name: Amy
//#> Last  name: Smith
//#> Age: 19
```

> The program uses `#include <sstream>` for access to the string stream class, which is in `namespace std`. The line `istringstream inSS(userInfo);` declares a new stream variable and initializes its buffer to a copy of `userInfo`. Then, the program can extract data from stream `inSS` using `>>` similar to extracting from `cin`.
> .
> A common use of string streams is to process user input line-by-line. The following program reads in the line as a string, and then extracts individual data items from that string.

```cpp
#include <iostream>
#include <string>
#include <sstream>
using namespace std;

int main() {
   istringstream inSS;       // Input string stream
   string lineString;        // Holds line of text
   string firstName;         // First name
   string lastName;          // Last name
   int    userAge = 0;       // Age
   bool   inputDone = false; // Flag to indicate next iteration
   
   // Prompt user for input
   cout << "Enter \"firstname lastname age\" on each line" << endl;
   cout << "(\"Exit\" as firstname exits)." << endl << endl;
   
   // Grab data as long as "Exit" is not entered
   while (!inputDone) {
      
      // Entire line into lineString
      getline(cin, lineString);
      
      // Copies to inSS's string buffer
      inSS.clear();
      inSS.str(lineString);
      
      // Now process the line
      inSS >> firstName;
      
      // Output parsed values
      if (firstName == "Exit") {
         cout << "   Exiting." << endl;
         
         inputDone = true;
      }
      else {
         inSS >> lastName;
         inSS >> userAge;
         
         cout << "   First name: " << firstName << endl;
         cout << "   Last  name: " << lastName << endl;
         cout << "   Age:        " << userAge   << endl;
         cout << endl;
      }
   }
   
   return 0;
}

//#> Enter "firstname lastname age" on each line
//#> ("Exit" as firstname exits).
//#> 
//#> Mary Jones 22
//#>    First name: Mary
//#>    Last  name: Jones
//#>    Age:        22
//#> 
//#> Sally Smith 14
//#>    First name: Sally
//#>    Last  name: Smith
//#>    Age:        14
//#> 
//#> Exit
//#>    Exiting.
```

#### Output Stream

> The program uses `getline` to read an input line into a string. The line `inSS.str(lineString);` uses the `str(s)` function to initialize the stream's buffer to string `s`. Afterwards, the program extracts input from that stream using `>>.` The statement `inSS.clear();` is necessary to reset the state of the stream so that subsequent extractions start from the beginning; the clear resets the stream's state.
> .
> Similarly, a new output string stream variable of type **ostringstream** can be created that is associated with a string rather than with the screen (standard output). **ostringstream** is a special kind of (i.e., is derived from) `ostream`. Once created, a program can insert characters into that stream using `<<`, as follows.

```cpp
#include <iostream>
#include <string>
#include <sstream>
using namespace std;

int main() {
   ostringstream fullNameOSS; // Output string stream
   ostringstream ageOSS;      // Output string stream
   string firstName;          // First name
   string lastName;           // Last name
   string fullName;           // Full name (first and last)
   string ageStr;             // Age (string)
   int userAge = 0;           // Age
   
   // Prompt user for input
   cout << "Enter \"firstname lastname age\": " << endl;
   cin >> firstName;
   cin >> lastName;
   cin >> userAge;
   
   // Writes to buffer, then copies from buffer into string
   fullNameOSS << lastName << ", " << firstName;
   fullName = fullNameOSS.str();
   
   // Output parsed input
   cout << endl << "   Full name: " << fullName << endl;
   
   // Writes int age as chars to buffer
   ageOSS << userAge;
   
   // Appends (minor) to buffer if less than 21, then
   // copies buffer into string
   if (userAge < 21) {
      ageOSS << " (minor)";
   }
   
   ageStr = ageOSS.str();
   
   // Output string
   cout << "   Age: " << ageStr << endl;
   
   return 0;
}
```
