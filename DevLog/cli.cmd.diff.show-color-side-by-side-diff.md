---
id: T3dk0gvZ9aTVRiGGJvOaz
title: Show Color Side by Side Diff
desc: ''
updated: 1644535567981
created: 1641185251169
---

```bash
diff --color=always --minimal --side-by-side file1 file2
```

- Shows **red**/_green_ diff of 2 files side by side
- `file1` is the first arg and so it is on the left
- `file2` therefore is on the right

Write diff output to a file

```bash
diff --color=always --minimal --side-by-side file1 file2 > output_file.diff
```
