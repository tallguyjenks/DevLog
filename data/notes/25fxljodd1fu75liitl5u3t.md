

### Stream Errors

> A **stream error** occurs when insertion or extraction fails, causing the stream to enter an error state.

```cpp
#include <iostream>
using namespace std;

int main() {
   int num1 = -1; // Initial value -1 for demo purposes.
   int num2 = -1;
   
   cout << "Enter a number: " << endl;
   cin  >> num1; // Stream error state entered here.
   
   cout << "Enter a second number:" << endl;
   cin  >> num2; // Stream already in error state, so extraction skipped.
   
   cout << "num1: " << num1 << endl;
   cout << "num2: " << num2 << endl;
   
   return 0;
}

/*
	Enter a number:
	six
	Enter a second number:
	num1: 0
	num2: -1
*/

```

> A stream's error state can be checked with a function. Ex: `cin.good() `returns true if `cin` is not in an error state. Otherwise, false is returned. A stream internally uses several 1-bit error flags to track the state of the stream.

| Flag      | Meaning                                                                                                                       | Function                                                                                                         |
| :-------- | :---------------------------------------------------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------------------- |
| `goodbit` | Indicates no error flags are set and the stream is good.                                                                      | `good()` returns true if no stream errors have occurred.                                                         |
| `eofbit`  | Indicates if end-of-file reached on extraction.                                                                               | `eof()` returns value of eofbit, if end-of-file reached on extraction.                                           |
| `failbit` | Indicates a logical error for the previous extraction or insertion operation.                                                 | `fail()` returns true if either failbit or badbit is set, indicating an error for the previous stream operation. |
| `badbit`  | Indicates an error occurred reading or writing the stream, and the stream is bad. Further operations on the stream will fail. | `bad()` returns true if badbit is set, indicating the stream is bad.                                             |

> A stream's error state is cleared using `clear()`. Ex: `cin.clear()` clears the error state from `cin`.
> .
> The function `ignore(maxToIgnore, stopChar)` ignores characters in the stream buffer. Ex: `cin.ignore(10, '\n') `ignores up to 10 characters in the stream buffer, or until a '`\n`' character is encountered.
> .
> Commonly, a program needs to wait until a '`\n`' character is found, in which case set `maxToIgnore` to the maximum size of a stream: `numeric_limits<streamsize>::max()`.

```cpp
// Read user input until a number is entered
#include <iostream>
#include <limits>
using namespace std;

int main() {
   int number = 0;
   
   cout << "Enter a number: " << endl;
   cin >> number;
   
   while (cin.fail()) {
      // Clear error state
      cin.clear();

      // Ignore characters in stream until newline
      cin.ignore(numeric_limits<streamsize>::max(), '\n');
      
      cout << "Try again: " << endl;
      cin  >> number;
   }
   
   cout << "You entered: " << number << endl;
   
   return 0;
}
```

> A program may need to check for errors during file reading. 
> One approach is to check whether end-of-file was reached after the file reading ends. If end-of-file was not reached, then an error in file reading occurred.

```cpp
/* Given:
	myfile.txt:
	5
	8
	six
	4
	6
*/

#include <iostream>
#include <fstream>
using namespace std;

int main() {
   ifstream inFS;
   int fileNumber = 0; // Number in file
   
   inFS.open("myfile.txt");
   
   if (!inFS.is_open()) {
      cout << "Could not open file myfile.txt." << endl;
      
      return 1;
   }
   
   // Read file until end-of-file or an error
   while (inFS.good()) {
       inFS >> fileNumber;
       cout << "File number: " << fileNumber << endl;
   }
   
   // If end-of-file not reached, then an error occurred
   if (!inFS.eof()) {
      cout << "Error reading myfile.txt" << endl;
      
      return 1;
   }
   
   inFS.close();
   
   return 0;
}

/*
	File number: 5
	File number: 8
	File number: 0
	Error reading myfile.txt
*/
```
