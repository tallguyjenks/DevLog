---
id: 11jv9ega6a0b0x7qez7psz6
title: Ordered
desc: ''
updated: 1641412433771
created: 1641412433771
---


## Ordered Lists

ordered lists can be explicitly numbered

```
1. First item
2. Second item
3. Third item
4. Fourth item
```

Or they will be automatically numbered based on order and indentation

```
1. First item
1. Second item
1. Third item
1. Fourth item
```

becomes:

```
1. First item
2. Second item
3. Third item
4. Fourth item
```

Indentation levels reset the counts for each instance of a sublist

1. First item
2. Second item
3. Third item
   1. Indented item
   2. Indented item
4. Fourth item

Even when unordered the relative links still work correctly

```
1. First item
1. Second item
1. Third item
    1. Indented item
    1. Indented item
1. Fourth item
```

becomes:

```
1. First item
2. Second item
3. Third item
    1. Indented item
    2. Indented item
4. Fourth item
```
