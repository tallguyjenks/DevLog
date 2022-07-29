

#### Text Formatting

| Manipulator | Description                                                                                                                                                                                             | Example (for item "Amy")    |   |
| :---------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | :-------------------------- | - |
| setw(n)     | Sets the number of characters for the next output item only (does not persist, in contrast to other manipulators). By default, the item will be right-aligned, and filled with spaces. From `<iomanip>` | For n=7: "Amy"              |   |
| setfill(c)  | Sets the fill to character c. From `<iomanip>`                                                                                                                                                          | For c='\*': ""\*\*\*\*Amy"" | " |
| left        | Changes to left alignment. From `<ios>`                                                                                                                                                                 | "Amy "                      |   |
| right       | Changes to right alignment. From `<ios>`                                                                                                                                                                | " Amy"                      |   |

```cpp
#include <iostream>
#include <ios>
#include <iomanip>
using namespace std;

int main() {
   cout << "Dog age in human years (dogyears.com)" << endl << endl;
   
   // set num char for each column, set alignment
   cout << setw(10) << left  << "Dog age" << "|";
   cout << setw(12) << right << "Human age" << endl;
   cout << "------------------------------" << endl;
   cout << setw(10) << left  << "2 months" << "|";
   cout << setw(12) << right << "14 months" << endl;
   cout << setw(10) << left  << "6 months" << "|";
   cout << setw(12) << right << "5 years" << endl;
   
   // set fill character, num char for each column, set alignment
   cout << setfill('-');
   cout << setw(10) << left  << "8 months" << "|";
   cout << setw(12) << right << "9 years" << endl;
   cout << setw(10) << left  << "1 year" << "|";
   
   // change fill character, num char for each column, set alignment
   cout << setfill('.');
   cout << setw(12) << right << "15 years" << endl;

   // change fill character, num char for each column
   cout << setfill('*') << setw(30) << "" << endl;
   
   return 0;
}
```

> Of particular interest is how the `setw()` and `setfill()` manipulators are used in the last few lines. Note how they are used to create a line of 30 asterisks, without having to type 30 asterisks.
> .
> Most manipulators are persistent, meaning they change the state of the stream for all subsequent output. The exception is `setw()`, which <u>only affects the next output item</u>, defined that way likely because programmers usually only want to set the width of the next item and not all subsequent items.

| Manipulator | Description                                                                                           |                   |
| :---------: | :---------------------------------------------------------------------------------------------------- | ----------------- |
|    `endl`   | Inserts a newline character '\\n' into the output buffer, and informs the system to flush the buffer. | From `<iostream>` |
|   `flush`   | Informs the system to flush the buffer. From `<iostream>`                                             |                   |
