

##### Colorized Output In Bash

- Using ANSI escape codes you can make your terminal display colored output

|     Color    |      Code      |     Color    |      Code      |
| :----------: | :------------: | :----------: | :------------: |
|     Black    | '\\033\[0;30m' |   Dark Gray  | '\\033\[1;30m' |
|      Red     | '\\033\[0;31m' |   Light Red  | '\\033\[1;31m' |
|     Green    | '\\033\[0;32m' |  Light Green | '\\033\[1;32m' |
| Brown/Orange | '\\033\[0;33m' |    Yellow    | '\\033\[1;33m' |
|     Blue     | '\\033\[0;34m' |  Light Blue  | '\\033\[1;34m' |
|    Purple    | '\\033\[0;35m' | Light Purple | '\\033\[1;35m' |
|     Cyan     | '\\033\[0;36m' |  Light Cyan  | '\\033\[1;36m' |
|  Light Gray  | '\\033\[0;37m' |     White    | '\\033\[1;37m' |

- `RED='\033[0;31m'`
- 30-37 sets foreground color
- 40-47 sets background color

```bash
RED='\033[0;31m'
NC='\033[0m'

echo -e "${LRED}Hard${NC} [1]   ${RED}Difficult${NC} [2]   ${YELLOW}Normal${NC} [3]   ${GREEN}Mild${NC} [4]   ${LGREEN}Easy${NC} [5]"
```

###### Documentation

- [SO answer](https://stackoverflow.com/questions/5947742/how-to-change-the-output-color-of-echo-in-linux#5947802)
- [more documentation](https://misc.flogisoft.com/bash/tip_colors_and_formatting)
