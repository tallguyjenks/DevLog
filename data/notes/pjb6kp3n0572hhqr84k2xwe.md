

## Class Code Separation of Concerns

Typically 2 files are used to separate class code:

`ClassName.h` **--** _Contains the class definition, including data members and member function declarations._

`ClassName.cpp` **--**	_Contains member function definitions._

> Sometimes multiple small related classes are grouped into a single file, to avoid a proliferation of files. But for typical classes, good practice is to create a unique `.cpp` and `.h` file for each class.
