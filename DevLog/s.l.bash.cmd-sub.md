---
id: vmgslf9i423bpf9ip4y6c6u
title: Cmd Sub
desc: ''
updated: 1641429393847
created: 1641429393847
---


#### Command Substitution

- `( [command list] )`
- Execute the list of commands in a subshell.
- This is exactly the same thing as the command grouping above, only, the commands are executed in a subshell. Any code that affects the environment such as variable assignments, cd, export, etc. do not affect the main script's environment but are scoped within the brackets.
- **\*Note:** You do not need a `;` before the closing `)`.
