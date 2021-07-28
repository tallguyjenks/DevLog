---
tags:
#  - 🌱️
#  - 🌞️
#  - 🌲️
#  - ⚙️ 
#  - 🏷️ 
#  - 🗺️
aliases: 
  - Tables
#cssclass: []
---

#### [[Markdown Tables]]

---

In markdown the tables are denoted with pipe characters `|` 

There is a minimum of 3 rows for a table

1. header names
2. separator
3. data row

| Syntax    | Description |
| --------- | ----------- |
| Header    | Title       |
| Paragraph | Text        |

code:

```
| Syntax    | Description |
| --------- | ----------- |
| Header    | Title       |
| Paragraph | Text        |
```

---

The separator row has some options

`|:---|`: Align content of this column **Left**

```
| Syntax    | Description |
|:--------- |:----------- |
| Header    | Title       |
| Paragraph | Text        |
```

| Syntax    | Description |
|:--------- |:----------- |
| Header    | Title       |
| Paragraph | Text        |

---

`|---:|`: Align content of this column **Right**

```
|    Syntax | Description |
| ---------:| -----------:|
|    Header |       Title |
| Paragraph |        Text |
```

|    Syntax | Description |
| ---------:| -----------:|
|    Header |       Title |
| Paragraph |        Text |

---

`|:---:|`: Align content of this column **Center**

```
|  Syntax   | Description |
|:---------:|:-----------:|
|  Header   |    Title    |
| Paragraph |    Text     |
```

|  Syntax   | Description |
|:---------:|:-----------:|
|  Header   |    Title    |
| Paragraph |    Text     |

Rendering may differ. See 3rd party plugin for Advanced Tables for easy management of markdown tables

Content within the table can contain:
- [[Markdown Font Formatting|Font Formatting]]
- [[Markdown Images|Images]]
- [[Markdown Links|Links]]

---
Tags: 

Reference:

Related:
