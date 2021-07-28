## Data Types
	- Normal variables are usually camel case with first letter lower case `likeThis`
	  
	  variables must have their data types declared before the name of the variable
	- ### Integer
	  collapsed:: true
		- *Whole numbers only.*
		-
		  ```c++
		  int age = 28;
		  ```
		- #### Other types of Integers
			-
			  |Declaration|Size|Supported number range|Standard-defined minimum size|
			  |------|------|------|------|
			  |`char myVar;`|8 bits|-128 to 127|8 bits|
			  |`short myVar;`|16 bits|-32,768 to 32,767|16 bits|
			  |`long myVar;`|32 bits|-2,147,483,648 to 2,147,483,647|32 bits|
			  |`long long myVar;`|64 bits|-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807|64 bits|
			  |`int myVar;`|32 bits|-2,147,483,648 to 2,147,483,647|16 bits|
		- #### Unsigned Integers
			- If you know an integer will always be positive then you can double the range of the positive value limit as the negative value limit will be reduced to zero in favor of expanding the positive limit.
			-
			  |Declaration|Size|Supported number range|Standard-defined minimum size|
			  |------|------|------|------|
			  |`unsigned char myVar;`|8 bits|0 to 255|8 bits|
			  |`unsigned short myVar;`|16 bits|0 to 65,535|16 bits|
			  |`unsigned long myVar;`|32 bits|0 to 4,294,967,295|32 bits|
			  |`unsigned long long myVar;`|64 bits|0 to 184,467,440,737,095,551,615|64 bits|
			  |`unsigned int myVar;`|32 bits|0 to 4,294,967,295|16 bits|
	- ### Double / Float
		- *Floating point numbers "They have a decimal point", can be 1.0 like an integer but can also be 1.1.*
		-
		  ```c++
		  double heightInCentimeters = 198.7;
		  ```
	- ### Character
		- *Character are a single character only, and in the assignment the character must be wrapped in single quotes.*
		-
		  ```c++
		  char arrowBody = '-'
		  ```
	- ### Boolean
		- *booleans can hold the values `true` and `false` that is all.*
		- A great practice for boolean variables would be to name them something beginning with the word *is* like `isTall` the answer to their question is `true` or `false`. This makes code easier to understand.
		-
		  ```c++
		  bool isLarge = true;
		  bool isNeg   = false;
		  ```
	- ### Strings
		- *Strings make use of the [[C++ Include string|string]] library to represent an array of characters (a word or more) in a single datatype with minimal headache on management and more options and functionality than C-style strings*
		-
		  ```c++
		  string firstName = "bryan";
		  ```
		- If you are reading in^[[[C++ Basic Input Output]]] a string value into a variable, any spaces will be considered the termination of the string.
		- To get the entire input string you need to use `getline()`
		-
		  ```c++
		  string firstName;
		  string lastName;
		  cout << "Enter first name:" << endl;
		  getline(cin, firstName); // Gets entire line up to ENTER
		  cout << "Enter last name:" << endl;
		  getline(cin, lastName); // Gets entire line up to ENTER
		  cout << endl;
		  cout << "Welcome " << firstName << " " << lastName << "!" << endl;
		  cout << "May I call you " << firstName << "?" << endl;
		  ```
		- #### C Strings
			- char arrays were the only type of strings that existed in `C` such as:
			-
			  ```c++
			  char movieTitle[20] = "Star Wars";
			  ```
			-
			  > Because a string can be shorter than the character array, a string in a char array must end with a special character known as a null character, written as '\\0'. Given a string literal like "Star Wars", the compiler automatically appends a null character.
			  > .
			  > A char array of size 20 can store strings of lengths 0 to 19. The longest string is 19, not 20, since the null character must be stored.
			- `C` strings can be in legacy code and are included with:
			-
			  ```c++
			  #include <cstring>
			  ```
			- See [[C++ Include cstring]]
	- ### Auto
		- The `auto` specifier is a way of detecting the data type based on assignment value.
		-
		  ```c++
		  auto i = 5;   // causes i to be of type int
		  	  // and
		  auto j = 5.0; // causes j to be of type double.
		  ```
## Mutability
	- `const` variables are traditionally upper snake case `LIKE_THIS`
	  
	  To declare something as `const` is to make it immutable and unable to be reassigned to a new value.
	-
	  ```c++
	  const int CENTIMETERS_PER_INCH = 3; // will forever be 3
	  ```
## Related:
	- TODO [[Bash Variables]] fix this link
	  todo:: 1627450642129
	- Python ((6100ca2b-21a1-4fbe-babf-ada8c983a200))