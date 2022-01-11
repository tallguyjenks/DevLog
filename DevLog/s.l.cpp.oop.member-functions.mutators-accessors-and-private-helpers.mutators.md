---
id: JV3B9aLnmIJ9TMdpcKmOI
title: Mutators
desc: ''
updated: 1641372392592
created: 1641372392592
---

### Mutators

Modify / 'Mutate' the data members of a class (a setter, it sets the value of a data member by changing it)

```cpp
// Public member function. Setter / Mutator
public:
	void SetPlayer1PlayA(int playScore); // Mutator

// Private data member that users cant access
private:
	int player1PlayA;

// Function definition, get input value and set private data member
// value equal to that input
void GameInfo::SetPlayer1PlayA(int playScore) {
   player1PlayA = playScore;
}
```