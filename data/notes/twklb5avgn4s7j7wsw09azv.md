

| Convention  | Description                                                                            | Explanation                                                                                                                |
| ----------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| `( )`       | Items within parentheses are evaluated first.                                          | In !(age > 16), age > 16 is evaluated first, then the logical NOT.                                                         |
| `!`         | Next to be evaluated is !.                                                             |                                                                                                                            |
| `* / % + -` | Arithmetic operator are then evaluated using the precedence rules for those operators. | z - 45 &lt; 53 is evaluated as (z - 45) &lt; 53.                                                                           |
| `< <= > >=` | Then, relational operators &lt; &lt;= > >= are evaluated.                              | x &lt; 2 \|\| x >= 10 is evaluated as (x &lt; 2) \|\| (x >= 10) because &lt; and >= have precedence over \|\|.             |
| `==   !=`   | Then, the equality and inequality operators == != are evaluated.                       | x == 0 && x >= 10 is evaluated as (x == 0) && (x >= 10) because &lt; and >= have precedence over &&lt;.                    |
| `&`         | Then, the bitwise AND operator is evaluated.                                           | x == 5 \| y == 10 & z != 10 is evaluated as (x == 5) \| ((y == 10) & (z != 10)) because & has precedence over \|.          |
| \|          | Then, the bitwise OR operator is evaluated.                                            | x == 5 \| y == 10 && z != 10 is evaluated as ((x == 5) \| (y == 10)) && (z != 10)) because \| has precedence over &&.      |
| `&&`        | Then, the logical AND operator is evaluated.                                           | x == 5 \|\| y == 10 && z != 10 is evaluated as (x == 5) \|\| ((y == 10) && (z != 10)) because && has precedence over \|\|. |
| \|\|        | Finally, the logical OR operator is evaluated.                                         |                                                                                                                            |
