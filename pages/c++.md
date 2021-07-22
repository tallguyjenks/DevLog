- **Language**
	- ^^Setup^^
	- ^^Resources^^
		- [Assembly Code Breakdown of your code](https://godbolt.org/)
		- [cplusplus.com](http://cplusplus.com/reference/)
		- [Cherno C++ Tutorial Series](https://www.youtube.com/playlist?list=PLlrATfBNZ98dudnM48yfGUldqGD0S4FFb)
	- ^^Tools^^
	- ^^Libraries^^
	- ^^Projects^^
	- ^^Syntax^^
		- **Basic Input / Output**
			-
			  ```c++
			  /*
			  	Basic input output
			  	Send to STDOUT
			  	endl is like "\n" but better
			  */
			  
			  std::cout << "What are you ending to the terminal?" << std::endl;
			  //#> What are you ending to the terminal?
			  
			  std::cin >> myVariable; // "Hello World"
			  
			  std::cout << "this goes to terminal: " << myVariable << std::endl;
			  //#> this goes to terminal: Hello World
			  ```
		- **Precedence rules for logical and relational operators**
			-
			  |Convention|Description|Explanation|
			  |--------|--------|--------|
			  |`( )`|Items within parentheses are evaluated first.|In !(age > 16), age > 16 is evaluated first, then the logical NOT.|
			  |`!`|Next to be evaluated is !.||
			  |`* / % + -`|Arithmetic operator are then evaluated using the precedence rules for those operators.|z - 45 < 53 is evaluated as (z - 45) < 53.|
			  |`< <= > >=`|Then, relational operators < <= > >= are evaluated.|x < 2 \|\| x >= 10 is evaluated as (x < 2) \|\| (x >= 10) because < and >= have precedence over \|\|.|
			  |`==   !=`|Then, the equality and inequality operators == != are evaluated.|x == 0 && x >= 10 is evaluated as (x == 0) && (x >= 10) because < and >= have precedence over &&.|
			  |`&`|Then, the bitwise AND operator is evaluated.|x == 5 \| y == 10 & z != 10 is evaluated as (x == 5) \| ((y == 10) & (z != 10)) because & has precedence over \|.|
			  |\||Then, the bitwise OR operator is evaluated.|x == 5 \| y == 10 && z != 10 is evaluated as ((x == 5) \| (y == 10)) && (z != 10)) because \| has precedence over &&.|
			  |`&&`|Then, the logical AND operator is evaluated.|x == 5 \|\| y == 10 && z != 10 is evaluated as (x == 5) \|\| ((y == 10) && (z != 10)) because && has precedence over \|\|.|
			  |\|\||Finally, the logical OR operator is evaluated.
			-
	- ^^Data Types & Structs^^
	- ^^Flow Control^^
	- ^^Functions^^
	- ^^Object Oriented Programming^^
	- ^^File Handling^^
	- ^^Tips, Tricks, & Hacks^^