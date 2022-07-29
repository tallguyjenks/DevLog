

#### Text Case Modification In Bash

- I realize that this is beside your point, but…don't shell out to `tr` like you did. It's really slow and Bash has built-in facilities for manipulating strings—especially case. Equivalent to your code `input=$(echo "$value" | tr '[:upper:]' '[:lower:]')` would be something like:
- input="$\*"
- input="${input,,}"
- We are assigning a new value to the `bash` variable `input`.  The right-hand-side of the `=` is the new value. If we used `${input}`, that would just be the value already in variable `input` The magic is in those two commas `,,`. A `,` operator after the variable name downcases the first letter of the variable and leaves the rest of the value unchanged. The double-comma `,,` operator after the variable downcases every character in the value.
- You can use `^` and `==` for uppercasing.
- You could have done the same in a single line with `input="${*,,}"`
- I ran the `tr` version as written above 1000 times and a "pure" Bash equivalent The `tr` version took 4.1 sec versus "pure" Bash's 0.04 sec (100 X faster).

