---
id: ovs77tsslg1j5qhxvh9kcxm
title: If Else
desc: ''
updated: 1641371833360
created: 1641105063892
stub: false
isDir: false
---


## Single-Branch

```cpp
// Statements that execute before the branches

if (expression) {
   // Statements to execute when the expression is true (first branch)
} else {
   // Statements to execute when the expression is false (second branch)
}

// Statements that execute after the branches
```

## Multi-Branch

The more branches you add to an If-Statement the more it becomes advantageous to just use a case statement^\[[[C++ Case Statements|c++-case-statements]]]

```cpp
if (expr1) {
	
} else if (expr2) {
	
} else if (exprN) {
	
} else {

}
```

## Short Circuit Evaluation

> A logical operator evaluates operands from left to right. **Short circuit evaluation** skips evaluating later operands if the result of the logical operator can already be determined.

| Operator               | Example            | Short Circuit Evaluation                                                                                                |
| ---------------------- | ------------------ | ----------------------------------------------------------------------------------------------------------------------- |
| operand1 && operand2   | true && operand2   | If the first operand evaluates to true, operand2 is evaluated.                                                          |
| operand1 && operand2   | false && operand2  | If the first operand evaluates to false, the result of the AND operation is always false, so operand2 is not evaluated. |
| operand1 \|\| operand2 | true \|\| operand2 | If the first operand evaluates to true, the result of the OR operation is always true, so operand2 is not evaluated.    |
| operand1 \|\| operand2 | false \|\|operand2 | If the first operand evaluates to false, operand2 is evaluated.                                                         |
