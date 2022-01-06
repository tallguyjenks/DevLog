---
id: 2nTHM0FL0GINFHLGC5VCq
title: Refactoring Improving the Design of Existing Code
desc: ''
updated: 1641268084959
created: 1641168992635
stub: false
isDir: false
---

## Metadata

- `Author:` [[@martin-fowler]]
  - `Notable Authors:` [[kent-beck]]
- `ISBN:` 978-0-13-475759-9
- `Publish Date:` 1999-06-28

## Notes:

---

- Notes like this: `Extract Function (106)` 
  - mean that on `Page 106` there is a better example of that concept

---

- [[Refactoring Extract Function 106|refactoring-extract-function-106]]
- [[Refactoring Inline Variable 123|refactoring-inline-variable-123]]
- [[Refactoring Change Function Declaration 124|refactoring-change-function-declaration-124]]
- [ ] [[Refactoring Split Phase 154|refactoring-split-phase-154]]
- [ ] [[Refactoring Replace Temp With Query 178|refactoring-replace-temp-with-query-178]]
- [ ] [[Refactoring Move Function 198|refactoring-move-function-198]]
- [ ] [[Refactoring Slide Statements 223|refactoring-slide-statements-223]]
- [ ] [[Refactoring Split Loop 227|refactoring-split-loop-227]]
- [ ] [[Refactoring Replace Loop With Pipeline 231|refactoring-replace-loop-with-pipeline-231]]
- [ ] [[Refactoring Replace Conditional With Polymorphism 272|refactoring-replace-conditional-with-polymorphism-272]]
- [ ] [Refactoring Introduce Assertion 302]]
- [ ] [[Refactoring Replace Constructor With Factory Function 334|refactoring-replace-constructor-with-factory-function-334]]
- [ ] [[Refactoring Replace Type Code With Subclasses 362|refactoring-replace-type-code-with-subclasses-362]]

---

### Chapter 1 Refactoring: A First Example

---

- First step in refactoring is to ensure that there is a solid set of tests for the section of code to ensure that functionality is not altered
- Immediately compile/run the code after a change along with the test quite to check for unintended changes
- Incrementally save and commit to VCS to easily return to prior state, squash merge later for the actual merge of the refactoring into [[cli.cmd.git]]
- Even if the result of a refactor is more loops and more loop iterations and what "appears" to be more inefficient code
  - sometimes the increased inefficiency is negligible or justifiably worth it for cleaner, simpler, more legible code. 
  - If performance takes a big hit then it may warrant performance tuning after the refactor to try and speed it back up or even a revert of the refactor

---

### Chapter 2

---

<++>

---
