
## Chapter 1 Refactoring: A First Example

---

- First step in refactoring is to ensure that there is a solid set of tests for the section of code to ensure that functionality is not altered
- Immediately compile/run the code after a change along with the test quite to check for unintended changes
- Incrementally save and commit to VCS to easily return to prior state, squash merge later for the actual merge of the refactoring into [[cli.cmd.git]]
- Even if the result of a refactor is more loops and more loop iterations and what "appears" to be more inefficient code
  - sometimes the increased inefficiency is negligible or justifiably worth it for cleaner, simpler, more legible code.
  - If performance takes a big hit then it may warrant performance tuning after the refactor to try and speed it back up or even a revert of the refactor

---
