

## Chapter 2

---

- Refactoring is for when i need to understand the code base
  - If the code is a hot mess but i dont need to interact with it beyond treating it like an API black box then i can ignore the code for now. It's when i need to care that i refactor
  - If the code is easier to re-write than refactor that is also a valid edge case to not refactor
- Client boundries can get in the way such as the published public interface
  - If we want people to avoid using the `circum()` function in favor of the `circumference()` function then like the example in [[r.{.refactoring-improving-the-design-of-existing-code.refactorings.124-change-function-declaration]] leave the old declaration as a pass through with a deprecation warning and phase out over time. This is just the cost and fact of life for public interfaces and code ownership boundries.
- reduce the complexity of large branch feature merges with things like feature toggles to turn off "in-progress" work that is unable to be broken into smaller parts in a [[terms.ci-cd]] environment.

---
