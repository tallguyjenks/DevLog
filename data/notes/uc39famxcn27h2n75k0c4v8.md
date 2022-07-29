

### Input

> Sometimes a program should get input from a file rather than from a user typing on a keyboard. To achieve this, a programmer can create a new input stream that comes from a file, rather than the predefined input stream `cin` that comes from the standard input (keyboard). That new input stream can then be used just like `cin`, as the following program illustrates. Assume a text file exists named _myfile.txt_ with the contents shown (created for example using Notepad on a Windows computer or using TextEdit on a Mac computer).

```
myfile.txt with two integers:
5
10
```

```cpp
#include <iostream>
#include <fstream>
using namespace std;

int main() {
   ifstream inFS;     // Input file stream
   int fileNum1 = 0;  // Data value from file
   int fileNum2 = 0;  // Data value from file
   
   // Try to open file
   cout << "Opening file myfile.txt." << endl;
   
   inFS.open("myfile.txt");
   if (!inFS.is_open()) {
      cout << "Could not open file myfile.txt." << endl;
      return 1; // 1 indicates error
   }
   
   // Can now use inFS stream like cin stream
   // myfile.txt should contain two integers, else problems
   cout << "Reading two integers." << endl;
   inFS >> fileNum1;
   inFS >> fileNum2;
   cout << "Closing file myfile.txt." << endl;
   inFS.close(); // Done with file, so close it
   
   // Ouput values read from file
   cout << "num1: " << fileNum1 << endl;
   cout << "num2: " << fileNum2 << endl;
   cout << "num1 + num2: " << (fileNum1 + fileNum2) << endl;
   
   return 0;
}
```

> **Five** lines are needed for the new input stream, highlighted above.
> .
>
> - The `#include <fstream>` (for "_file stream_") enables use of the file stream class.
> - A new stream variable has been declared: `ifstream inFS;`. `ifstream` is short for _input file stream_, and is derived from `istream`.
> - The line `inFS.open("myfile.txt");` opens the file for reading and associates the file with the `inFS` stream. Because of the high likelihood that the open fails, usually because the file does not exist or is in use by another program, the program checks whether the open was successful using `if (!inFS.is_open())`.
> - The successfully opened input stream can then be used just like the `cin` stream, e.g., using `inFS >> num1;` to read an integer into `num1`.
> - Finally, when done using the stream, the program closes the file using `inFS.close()`.
> - A common error is to type `cin >> num1;` when actually intending to get data from a file as in `inFS >> num1`. Another common error is a mismatch between the variable data type and the file data, e.g., if the data type is int but the file data is "Hello".

> The `inFS.open(str)` function has a string parameter str, which can be a C++ string or a null-terminated C string. A program often uses a user-entered string as the filename, such as using `cin >> filename;`.

```cpp
/* Given

datafile.txt with two integers:
72
68

*/

#include <iostream>
#include <fstream>
#include <string>
using namespace std;

int main() {
   ifstream inFS;        // Input file stream
   int fileNum1 = 0;     // File data
   int fileNum2 = 0;     // File data
   string filename = ""; // Input filename
   
   // Prompt user for filename
   cout << "Enter filename: " << endl;
   cin >> filename;
   
   // Try to open file
   inFS.open(filename);
   
   if (!inFS.is_open()) {
      cout << "Could not open file " << filename << endl;
      return 1;
   }
   
   // Get numbers. If too few, may encounter problems
   inFS >> fileNum1;
   inFS >> fileNum2;
   
   // Done with file, close it
   inFS.close();
   
   // Ouput values read from file
   cout << "num1: " << fileNum1 << endl;
   cout << "num2: " << fileNum2 << endl;
   cout << "num1 + num2: " << (fileNum1 + fileNum2) << endl;
   
   return 0;
}

/*
	Enter filename: 
	datafile.txt
	num1: 72
	num2: 68
	num1 + num2: 140
*/
```

> A program can read varying amounts of data in a file by using a loop that reads until the end of the file has been reached, as follows.
> .
> The `eof()` function returns true if the previous stream operation reached the end of the file. Errors may be encountered while attempting to read from a file, including end-of-file, corrupt data, etc. So, a program should check that each read was successful before using the variable to which the data read was assigned. The `good()` function returns true if the previous stream operation had no problems. Ex:  `if( inFS.good() ) {...} `checks that the previous read operation was successful.

```cpp
/* Given:
	myfile.txt with variable number of integers:
	111
	222
	333
	444
	555
*/

#include <iostream>
#include <fstream>
using namespace std;

int main() {
   ifstream inFS;   // Input file stream
   int fileNum = 0; // File data
   
   // Open file
   cout << "Opening file myfile.txt." << endl;
   inFS.open("myfile.txt");
   
   if (!inFS.is_open()) {
      cout << "Could not open file myfile.txt." << endl;      
      return 1;
   }
   
   // Print read numbers to output
   cout << "Reading and printing numbers." << endl;
   
   while (!inFS.eof()) {
      inFS >> fileNum;
      if( inFS.good() ) {
         cout << "num: " << fileNum << endl;
      }
   }
   
   cout << "Closing file myfile.txt." << endl;
   
   // Done with file, so close it
   inFS.close();
   
   return 0;
}

/*
	Opening file myfile.txt.
	Reading and printing numbers.
	num: 111
	num: 222
	num: 333
	num: 444
	num: 555
	Closing file myfile.txt.
*/
```
