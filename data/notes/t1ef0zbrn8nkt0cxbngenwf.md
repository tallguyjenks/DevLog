

> > “Abstractions should not depend on details. Details should depend on abstraction. High-level modules should not depend on low-level modules. Both should depend on abstractions”
>
>  So, that abstractions (e.g., the interface, as seen above) should not be dependent on low-level methods but both should depend on a third interface.
> <br>
> To better explain this concept, I prefer to think of a sort of information flow.
> <br>
> Imagine that you have a program that takes in input a specific set of info (a file, a format, etc) and you wrote a script to process it.
> <br>
> What would happen if that info were subject to changes?
> <br>
> You would have to rewrite your script and adjust the new format. Losing the retro compatibility with the older files.
> <br>
> However, you could solve this by creating a third abstraction that takes the info as input and passes it to the others.
> This is basically what an API is also, used for.

![alt](assets/images/Pasted_image_20211110092721.png)

---

- ## Tags:
- Reference:
  - [[SOLID Coding in Python|r.(.2021.11.10.solid-coding-in-python]]
- Related:
  - [[Python Abstract Base Classes|s.l.python.oop.abstract-base-classes]]

