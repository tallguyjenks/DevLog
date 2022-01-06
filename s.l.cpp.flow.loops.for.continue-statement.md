---
id: EFN9De5pHEAscXzRy281E
title: Continue Statement
desc: ''
updated: 1641373217018
created: 1641373217018
---

## The continue Statement

```cpp
for ( int i = 0; i <= 19; i++ ) {
	if ( ( i % 10 ) == 0 ) {
		continue;
	}
	cout << i << endl;
}
```

The `continue;` statement will skip everything else in the loop and go to the next iteration of the loop.

In this case it will not send 10 to cout because it was told to continue on.
when the if condition found that the 10 was divisible by 10 with modulus division: `%`, it then ran `continue;` and said _"skip the printing of this value"_.
