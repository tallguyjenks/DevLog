---
id: hivz6swvklrph3gxhjef6je
title: Tables
desc: ''
updated: 1645136790988
created: 1645136698932
---

## Normal Tables

<https://docutils.sourceforge.io/docs/ref/rst/directives.html#table>

```rst
.. table:: Truth table for "not"
   :widths: auto

   =====  =====
     A    not A
   =====  =====
   False  True
   True   False
   =====  =====
```

## CSV Tables

<https://docutils.sourceforge.io/docs/ref/rst/directives.html#csv-table-1>

```rst
.. csv-table:: Frozen Delights!
   :header: "Treat", "Quantity", "Description"
   :widths: 15, 10, 30

   "Albatross", 2.99, "On a stick!"
   "Crunchy Frog", 1.49, "If we took the bones out, it wouldn't be
   crunchy, now would it?"
   "Gannet Ripple", 1.99, "On a stick!"
```

## List Tables

<https://docutils.sourceforge.io/docs/ref/rst/directives.html#list-table>

```rst
.. list-table:: Frozen Delights!
   :widths: 15 10 30
   :header-rows: 1

   * - Treat
     - Quantity
     - Description
   * - Albatross
     - 2.99
     - On a stick!
   * - Crunchy Frog
     - 1.49
     - If we took the bones out, it wouldn't be
       crunchy, now would it?
   * - Gannet Ripple
     - 1.99
     - On a stick!
```
