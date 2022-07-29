

### Extraction Before Getline

> The `getline()` function and the extraction operator `>>` handle a trailing newline differently, which can lead to a problem.
>
> - The `getline()` function reads a line of text from a buffer, **discarding the ending newline character**.
> - The extraction operator `>>` skips <u>whitespace</u>, then reads the next item such as an integer or string which is said to end at the next <u>whitespace</u>, leaving that ending whitespace character in the buffer (an exception being for reading a single character).

> The problem is that code like `cin >> myInt;` and `getline(cin, nextLine);` may not behave as expected if the integer is ended with a newline. The `getline()` function will read that single remaining newline character, returning an empty string, rather than proceeding to the next line.
> .
> A simple solution is to not mix the two approaches to reading an input buffer, either only using extraction, or only using `getline()`.
> .
> If one must mix the two approaches, then after an extraction operation, the trailing newline should be discarded from the buffer before calling the `getline()`, by inserting some statement in between. One possible solution inserts `cin.ignore()`, which discards the next character in the input buffer. Another possible approach inserts another `getline()` call, ignoring its blank string.
