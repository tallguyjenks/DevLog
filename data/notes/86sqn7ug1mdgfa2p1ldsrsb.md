

> A wildcard character is used to substitute one or more characters in a string
>
> <div class="signature"><a src="https://www.w3schools.com/sql/sql_wildcards.asp">w3schools</a></div>

---

| Symbol | Description                                         | Example                                  |
| :----- | :-------------------------------------------------- | :--------------------------------------- |
| `*`    | Represents zero or more characters                  | `bl*` finds bl, black, blue, and blob    |
| `?`    | Represents a single character                       | `h?t` finds hot, hat, and hit            |
| `[]`   | Represents any single character within the brackets | `h[oa]t` finds hot and hat, but not hit  |
| `^`    | Represents any character not in the brackets        | `h[^oa]t` finds hit, but not hot and hat |
| `-`    | Represents a range of characters                    | `c[a-b]t` finds cat and cbt              |
| `%`    | Represents zero or more characters                  | `bl%` finds bl, black, blue, and blob    |
| `_`    | Represents a single character                       | `h_t` finds hot, hat, and hit            |

---

Has to be used in conjunction with the `LIKE`  keyword as this is the trigger to run a search using these [[Regular Expressions|regular-expression]] "wild card" serrches.

---

- Reference:
  - [w3Schools](https://www.w3schools.com/sql/sql_wildcards.asp)

