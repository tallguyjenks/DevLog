---
id: 9tx8508057qa8h8axbm8f6a
title: Record Separator
desc: ''
updated: 1641269681201
created: 1641269681201
---


## Record Separator

> "Within a group (or table) the records are separated with RS or record separator."
> <br>
> We occasionally see CSV-ish files that use RS to separate records, which at first sounds defensible but honestly doesn't really help, because CSV authors just want to hit the enter key. And now your CSV parser has to support yet another newline.

---

> In the late 1970s, ASCII was extended by the ANSI standard to include additional control characters—to differentiate, the former are called C0 controls, the latter C1 controls. Using these new-fangled computer terminals of the day (such as 1978's VT100) could draw primitive graphics at arbitrary cursor locations. Aivosto Oy takes us on a helpful tour of these:
> <br>
> "According to ANSI, the C1 controls were intended for input/output control of two-dimensional character-imaging devices, including interactive terminals of both the cathode ray tube and printer types, as well as output to microfilm printers."
> <br>
> Evidently, the authors could not resist adding in a new-fangled newline amongst this fresh batch of characters.
