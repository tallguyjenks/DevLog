
Using the [[Markdown Lists|s.m.markdown.syntax.lists]] feature, tasks are just an additional syntax on top of the list syntax

## Syntax

```
- an uncompleted task
- [x] a completed task
	- an indented uncompleted task
	- [x] an indented completed task
```

In some processors completing the parent task to children tasks causes formatting such as strike through on sub items of the completed parent:

- an `uncompleted` task
- [x] a completed task
  - THIS IS UNCOMPLETED BUT IT'S PARENT IS COMPLETED
  - [x] an indented completed task

---

- Related:
  - [[Markdown Definition Lists|s.m.markdown.extended-functionality.definition-lists]]
