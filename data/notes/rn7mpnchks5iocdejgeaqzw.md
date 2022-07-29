

## Static Memory

> The region where global variables (_variables declared outside any function_) as well as static local variables (_variables declared inside functions starting with the keyword "static"_) are allocated. The name "static" comes from these variables not changing (_static means not changing_); they are allocated once and last for the duration of a program's execution, their addresses staying the same.

## The Stack

> The region where a function's local variables are allocated <u>during a function call</u>. A function call adds local variables to the stack, and a return removes them, like adding and removing dishes from a pile; hence the term "_stack_." Because this memory is automatically allocated and deallocated, it is also called **automatic memory**.

## The Heap

> The region where the "_new_" operator allocates memory, and where the "_delete_" operator deallocates memory. The region is also called **free store**.
