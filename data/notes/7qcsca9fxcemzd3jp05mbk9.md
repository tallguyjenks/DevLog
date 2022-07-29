

> “Functions that use pointers or references to base classes must be able to use objects of derived classes without knowing it”

Alternatively, this can be expressed as “Derived classes must be substitutable for their base classes”

> For example, the sub-class “Platypus”, of the base class “Mammals”, would have the exception that these mammals lay eggs. The LSP, tell us that it would create a function called “give_birth”, this function will have different behavior for the sub-class Platypus and the sub-class Dog. Therefore, we should have had a more abstract base class than Mammals that accommodate this.
>
> If this sounds very confusing, do not worry, the application of this latter aspect of the LSP is rarely fully implemented, and it rarely leaves the theoretical textbooks.

---

- Reference:
  - [[SOLID Coding in Python|r.(.2021.11.10.solid-coding-in-python]]

