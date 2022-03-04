---
id: vnltxkbxgntkr3tfdg8j10u
title: Regular Expressions
desc: ''
updated: 1641267600397
created: 1641105063864
stub: false
isDir: false
---


Useful site for writing and testing regex

- <https://www.regexpal.com/>
- <https://regex101.com/>
- <http://regextutorials.com/index.html>

![image.png](image_1626507098408_0.png)

Image Source: <https://twitter.com/manekinekko/status/1335330878403260419>

|        code         |                                                                                         Purpose                                                                                          |
| :-----------------: | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
|        `\d`         |                                                                                 represent any digit 0-9                                                                                  |
| `[0-9]` or `[abc]`  |                                            matches a range or any specfic item in the brackets could find a,b, or c but will find all of them                                            |
|        `\D`         |                                                                              match any NON-digit characters                                                                              |
| `[^0-9]` or `[^\d]` |                                                                  says match all BUT these in which case this is digits                                                                   |
|        `\w`         |            will match words, `\D` will match white space, punctuation, hyphens, etc. while `\w` does not. `\w` matches only letters and numbers, equivalently: `[a-zA-Z0-9]`             |
|        `\W`         |                                           to match a non word character. matches opposite of alphanumeric and is equivalent to `[^_a-zA-Z0-9]`                                           |
|        `\s`         |                                                                                 match a space character                                                                                  |
|        `\n`         |                                                                                         New line                                                                                         |
|        `\t`         |                                                                                          a tab                                                                                           |
|        `\r`         |                                                                                     carriage return                                                                                      |
|         `.`         |                                                                                match any single character                                                                                |
|        `\b`         | boundry, so for a word `\bA.{5}T\b` the boundries encompass words that start with 'A', end with 'T' and have 5 characters in the middle like ANCYENT or ANCIENT also akin to `\b\w{7}\b` |
|         `^`         |                                                                                beginning of a line anchor                                                                                |
|         `$`         |                                                                                   end of a line anchor                                                                                   |
|                     |                                                     the pipe is an 'or' statement in brackets is saying 't' OR 'T' in a regex search                                                     |
|    `[0-3[4-5]]`     |                   Union of 2 character sets, this would return 04, 05, 14, 15, 24, 25, 34, 35, this can also work with negation to use a set of 'NOT THESE' characters                   |

---

| Quantifier |                                                             Description                                                             |     |
| ---------- | :---------------------------------------------------------------------------------------------------------------------------------: | --- |
| `{8}`      | quantifyer, same as linux CLI `.{8}` would match any 8 characters, this one matches the patter a specific number of times, 8 times. |     |
| `{8,}`     |                                  the comma means it will match  or more occurances of the pattern                                   |     |
| `{2,4}`    |                         will match the pattern anytime it ocurs 2-4 times any of those options are captured                         |     |

