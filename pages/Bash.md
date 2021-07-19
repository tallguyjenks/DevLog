-
  > Bash is glue for C
- **Language**
	- ^^Setup^^
	- ^^Resources^^
	  collapsed:: true
		- [BashGuide](https://mywiki.wooledge.org/BashGuide)
		- [bash cheat sheet](https://mywiki.wooledge.org/BashSheet)
		- [pure bash bible](https://github.com/dylanaraps/pure-bash-bible)
		- [Cronjobs](https://crontab.guru/)
	- ^^Tools^^
	- ^^Libraries^^
	- ^^Projects^^
	  collapsed:: true
		- **Question Extractor Written In Bash**
			-
			  ```shell
			  if [[ -e $1 ]]
			  	then
			  filename="Questions $1"
			  count=$(grep -Fc '**Q**' "$1")
			  report="$count Questions extracted from $filename"
			  printf "# $report \n \n" > "./$filename"
			  grep -Fn '**Q**' "$1" | sed -e 's/\*\*Q:*\*\*:*//g' | sed -e 's/^/- /' >> "$filename"
			  echo $report
			  	else
			  echo Provide a file as an argument
			  fi
			  ```
			- This script will take a file as an input argument and then any lines it finds the text `**Q**` on it will extract into a list of questions in a new file called `questions_<input file name>` and also report in the CLI how many questions were extracted
	- ^^Syntax^^
	  collapsed:: true
		- ^^Variables^^
		  collapsed:: true
			- Variables in bash are assigned with a single `=`
			  No spacing between the variable name, the `=` and the assigned value
			  You can specify the variables scope with either `export` or `local` or
			  an environmental variable with no explicit scope.
			  
			  Once declared in your script or environment etc, you can reference your
			  variables by matching the exact casing of the variable name and pre-pending
			  a `$` so my path variable for binaries to execute would be `$PATH`.
			  
			  When referencing your variables always quote them because of:
			  "General rule: quote it if it can either be empty or contain spaces"
			  "`$?` doesn't need quotes since it's a numeric value."
			  
			  ```shell
			  ## Variables
			  
			  ### Local vars
			  local var=2
			  
			  ### Global Vars
			  var=2
			  
			  ### Environment
			  export var=2
			  
			  echo "$var"
			  ```
			  
			  "In short, quote everything where you do not require the shell to perform token
			  splitting and wild card expansion."
			  
			  ```shell
			  
			  ## Token Splitting
			  words="foo bar baz"
			  for word in $words; do
			      echo "$word"
			  done
			  #> foo
			  #> bar
			  #> baz
			  
			  ```
			  
			  Double quotes are suitable when variable interpolation is
			  required. With suitable adaptations, it is also a good workaround when you need
			  single quotes in the string. (There is no straightforward way to escape a
			  single quote between single quotes, because there is no escape mechanism inside
			  single quotes -- if there was, they would not quote completely verbatim.)
			  
			  No quotes are suitable when you specifically require the shell to perform token
			  splitting and/or wild card expansion.
			  
			  ```shell
			  ## Wildcard Expansion
			  
			  ### Literal Strings
			  pattern='file*.txt'
			  ls $pattern
			  # > file1.txt      file_other.txt
			  
			  ### Double Quotes
			  ls "$pattern"
			  #> ls: cannot access file*.txt: No such file or directory
			  # (There is no file named literally file*.txt.)
			  
			  ls '$pattern'
			  #> ls: cannot access $pattern: No such file or directory
			  # (There is no file named $pattern, either!)
			  ```
			  
			  In more concrete terms, anything containing a filename should usually be quoted
			  (because filenames can contain whitespace and other shell meta characters).
			  Anything containing a URL should usually be quoted (because many URL's contain
			  shell meta characters like `?` and `&`). Anything containing a regex should usually
			  be quoted (ditto ditto). Anything containing significant whitespace other than
			  single spaces between non-whitespace characters needs to be quoted (because
			  otherwise, the shell will munge the whitespace into, effectively, single
			  spaces, and trim any leading or trailing whitespace).
			  
			  When you know that a variable can only contain a value which contains no shell
			  meta characters, quoting is optional. Thus, an unquoted `$?` is basically fine,
			  because this variable can only ever contain a single number. However, `"$?"` is
			  also correct, and recommended for general consistency and correctness (though
			  this is my personal recommendation, not a widely recognized policy).
			  
			  Values which are not variables basically follow the same rules, though you
			  could then also escape any meta characters instead of quoting them. For a common
			  example, a URL with a & in it will be parsed by the shell as a background
			  command unless the meta character is escaped or quoted.
			- ## Types of Variables
			- `"$@"`
				- An array-like construct of all positional parameters, `{$1, $2, $3 ...}`
				- expands to the positional parameters starting from one.
				- When the expansion occurs within double quotes, each parameter expands to a separate word.
				- That is `"$@"` is equivalent to `"$1"` `"$2"` `"$3"`...
				- **Slicing**
					- `"${@:3}"` takes only arguments starting from the third `"$3"` onward
					- or argument ranges:
					-
					  ```shell 
					  echo "line1 ${@:1:1}"; #First argument
					  echo "line2 ${@:2:1}"; #Second argument
					  echo "line3 ${@:3}"; #Third argument onwards
					  ```
			- `"$1"`
				- Positional argument passed to a command `"$1"` in this instance: `echo "hello" "world"` is just `> hello`
			- `$0`
				- (generally the script's name or path) is not in `$@`.
			- `"$*"`
				- is the [[Internal Field Separator - IFS|IFS]] expansion of all positional parameters, `$1 $2 $3 ...`
			- `$?`
				- is the most recent foreground pipeline exit status.
			- `$#`
				- No quotes as its a numeric output
				- is the number of positional parameters.
			- `$IFS`
				- is the (input) field separator.
			- `$-`
				- current options set for the shell.
			- `$$`
				- pid of the current shell (not subshell).
			- `$_` 
			  	-most recent parameter (or the abs path of the command to start the current shell immediately after startup).
			- `$!`
				- is the PID of the most recent background command.
				  
				  [SO Source](https://stackoverflow.com/questions/3811345/how-to-pass-all-arguments-passed-to-my-bash-script-to-a-function-of-mine#3816747)
				  [SO Answer about $#](https://askubuntu.com/questions/939620/what-does-mean-in-bash)
				  [Comprehensive list of these](https://stackoverflow.com/questions/5163144/what-are-the-special-dollar-sign-shell-variables)
			- ## Here is a three-point formula for quotes in general:
			- ### *Double quotes*
			  
			  In contexts where we want to suppress word splitting and globbing. Also in
			  contexts where we want the literal to be treated as a string, not a regex.
			- ### *Single quotes*
			  
			  In string literals where we want to suppress interpolation and special
			  treatment of backslashes. In other words, situations where using double quotes
			  would be inappropriate.
			- ### *No quotes*
			  
			  In contexts where we are absolutely sure that there are no word splitting or
			  globbing issues or we do want word splitting and globbing.
			- ### *Examples*
			- #### _Double quotes_
			  
			   Literal strings with whitespace ("Stack Overflow rocks!", "Steve's Apple")
			    variable expansions (`"$var"`, `"${arr[@]}"`)
			    command substitutions (`"$(ls)"`, `"ls"`)
			    globs where directory path or file name part includes spaces (`"/my dir/"*`)
			    to protect single quotes (`"single'quote'delimited'string"`)
			    Bash parameter expansion (`"${filename##*/}"`)
			- #### _Single quotes_
			  
			   Command names and arguments that have whitespace in them literal strings that need interpolation to be suppressed  'Really costs \$\$!', 'just a backslash followed by a t: \t') to protect double quotes ('The "crux"') regex literals that need interpolation to be suppressed use shell quoting for literals involving special characters (`$'\n\t'`) use shell quoting where we need to protect several single and double quotes (`$'{"table": "users", "where": "first_name"=\'Steve\'}'`)
			- #### _No quotes_
			  
			   Around standard numeric variables (`$`, `$?`, `$#` etc.) in arithmetic contexts like ((count++)), `"${arr[idx]}"`, `"${string:start:length}"`
			    inside `[[ ]]` expression which is free from word splitting and globbing issues (this is a matter of style and opinions can vary widely) where we want word splitting (`for word in $words`) where we want globbing (`for txtfile in *.txt; do ...`) where we want ~ to be interpreted as `$HOME` (`~/"some dir" but not "~/some dir"`)
			  
			  ```shell
			  ## Non escaped meta characters
			  wget http://example.com/q&uack
			  #> [1] wget http://example.com/q
			  #> -bash: uack: command not found
			  
			  ### Single quotes is best or put into a variable
			  wget 'http://example.com/q&uack'  # Single quotes preferred for a static string
			  wget "http://example.com/q&uack"  # Double quotes work here, too (no $ or ` in the value)
			  wget http://example.com/q\&uack   # Backslash escape
			  wget http://example.com/q'&'uack  # Only the meta character really needs quoting
			  ```
			- ## Meta characters with variables
			  collapsed:: true
				- The braces, in addition to delimiting a variable name are used for parameter expansion so you can do things like:
				- Truncate the contents of a variable
				-
				  ```shell
				  var="abcde"; echo ${var%d*}
				  #> abc
				  ```
				- Make substitutions similar to sed
				-
				  ```shell
				  var="abcde"; echo ${var/de/12}
				  #> abc12
				  ```
				- Use a default value
				-
				  ```shell
				  default="hello"; unset var; echo ${var:-$default}
				  #> hello
				  ```
				- and several more
				- Also, brace expansions create lists of strings which are typically iterated
				  over in loops:
				-
				  ```shell
				  echo f{oo,ee,a}d
				  #> food feed fad
				  
				  mv error.log{,.OLD}
				  # (error.log is renamed to error.log.OLD because the brace expression
				  # expands to "mv error.log error.log.OLD")
				  
				  for num in {000..2}; do echo "$num"; done
				  #> 000
				  #> 001
				  #> 002
				  
				  echo {00..8..2}
				  #> 00 02 04 06 08
				  
				  echo {D..T..4}
				  #> D H L P T
				  ```
			- ## Double parentheses are used for arithmetic operations:
			  collapsed:: true
				-
				  ```shell
				  ((a++))
				  
				  ((meaning = 42))
				  
				  for ((i=0; i<10; i++))
				  
				  echo $((a + b + (14 * c)))
				  ```
				- and they enable you to omit the dollar signs on integer and array variables and include spaces around operators for readability.
				- Single brackets are also used for array indices:
				-
				  ```shell
				  array[4]="hello"
				  
				  element=${array[index]}
				  ```
			- ## Brackets 
			  collapsed:: true
				- http://wiki.bash-hackers.org/scripting/obsolete
				-
				  ```shell
				  if [ CONDITION ]    # Test construct
				  if [[ CONDITION ]]  # Extended test construct
				  Array[1]=element1   # Array initialization
				  [a-z]               # Range of characters within a Regular Expression
				  $[ expression ]     # A non-standard & obsolete version of $(( expression )) 
				  ```
			- ## Curly Braces
				-
				  ```shell
				  ${variable}                             # Parameter substitution
				  ${!variable}                            # Indirect variable reference
				  { command1; command2; . . . commandN; } # Block of code
				  {string1,string2,string3,...}           # Brace expansion
				  {a..z}                                  # Extended brace expansion
				  {}                                      # Text replacement, after find and xargs
				  ```
			- ## Parentheses
				-
				  ```shell
				  ( command1; command2 )             # Command group executed within a subshell
				  Array=(element1 element2 element3) # Array initialization
				  result=$(COMMAND)                  # Command substitution, new style
				  >(COMMAND)                         # Process substitution
				  <(COMMAND)                         # Process substitution
				  ```
			- ## Double Parentheses
				-
				  ```shell
				  (( var = 78 ))            # Integer arithmetic
				  var=$(( 20 + 5 ))         # Integer arithmetic, with variable assignment
				  (( var++ ))               # C-style variable increment
				  (( var-- ))               # C-style variable decrement
				  (( var0 = var1<98?9:21 )) # C-style ternary operation
				  ```
			- ## Exporting variables
				- Export variables for other programs to use in your shell environment with
				-
				  ```shell
				  export var=myvar
				  ```
				- Remove an exported variable with
				-
				  ```shell
				  unset myvar
				  ```
				- Export copies variables to the environment, `declare -x` also does the same as export?
				- Export functions with
				-
				  ```shell
				  export -f myfunc
				  ```
				- Just printing export will list all current environment variables
				- Functions don’t get a copy of the variables in the environment, they share them and therefor can mutate them
				- To see built-ins use
				-
				  ```shell
				  enable
				  ```
				- To see keywords use
				-
				  ```shell
				  compgen -k
				  ```
			- # Documentation
				- [bashtips](https://drawings.jvns.ca/bashtips/)
				- [quoting variables SO](https://stackoverflow.com/questions/10067266/when-to-wrap-quotes-around-a-shell-variable#10067297)
		- **Interpolation In Bash**
		  collapsed:: true
			- In computer programming, string interpolation is the process of evaluating a string literal containing one or more placeholders, yielding a result in which the placeholders are replaced with their corresponding values. It is a form of simple template processing or, in formal terms, a form of quasi-quotation.
			-
			  ```shell
			  #  Documentation
			  var="theres no place like '$HOME'"
			  echo "$var"
			  #> theres no place like /Users/bryanjenks
			  ```
			- **Documentation**
				- [Variable Interpolation](https://en.wikipedia.org/wiki/String_interpolation)
		- **IFS**
		  collapsed:: true
			- # Internal Field Separator - IFS
			  
			  IFS = Internal Field Separator.
			  Unbelievable as it may seem, [[POSIX]] requires the treatment of IFS as a field terminator, rather than a field separator. What this means in our example is that if there's an empty field at the end of the input line, it will be discarded:
			  
			  ```shell
			  
			  IFS=, read -ra fields <<< "a,b,"
			  declare -p fields
			  #> declare -a fields='([0]="a" [1]="b")'
			  
			  ```
			  
			  Where did the empty field go? It was eaten for historical reasons ("because it's always been that way"). This behavior is not unique to bash; all conforming shells do it. A non-empty field is properly scanned:
			  
			  ```shell
			  
			  IFS=, read -ra fields <<< "a,b,c"
			  declare -p fields
			  #> declare -a fields='([0]="a" [1]="b" [2]="c")'
			  
			  ```
			  
			  So, how do we work around this nonsense? As it turns out, appending an `IFS` character to the end of the input string will force the scanning to work. If there was a trailing empty field, the extra `IFS` character "terminates" it so that it gets scanned. If there was a trailing non-empty field, the `IFS` <character creates a new, empty field that gets dropped.
			  
			  ```shell
			  
			  input="a,b,"
			  IFS=, read -ra fields <<< "$input,"
			  declare -p fields
			  #> declare -a fields='([0]="a" [1]="b" [2]="")'
			  
			  ```
			- # Documentation
			  
			  <https://mywiki.wooledge.org/BashPitfalls>
			  <https://mywiki.wooledge.org/IFS>
		- **Text String Manipulation**
		  collapsed:: true
			- # Sub-String Removal In Bash
			  collapsed:: true
				- Removing substrings without `awk`/`cut` function calls
				-
				  ```shell
				  string="hello-world"
				  prefix="hell"
				  suffix="ld"
				  
				  foo=${string#"$prefix"}
				  foo=${foo%"$suffix"}
				  echo "${foo}"
				  #===#===#===#===#===#===#===#
				  string="hello-world"
				  prefix="hell"
				  suffix="ld"
				  
				  #remove "hell" from "hello-world" if "hell" is found at the beginning.
				  prefix_removed_string=${string/#$prefix}
				  
				  #remove "ld" from "o-world" if "ld" is found at the end.
				  suffix_removed_String=${prefix_removed_string/%$suffix}
				  echo $suffix_removed_String
				  #> o-wor
				  
				  # NOTES:
				  # `#$prefix` : adding `#` makes sure that substring "hell" is removed only if
				  # it is found in beginning.
				  # `%$suffix` : adding `%` makes sure that substring "ld" is removed only if it
				  # is found in end.
				  
				  # Without these, the substrings "hell" and "ld" will get removed everywhere,
				  # even it is found in the middle.
				  
				  var="apple orange"
				  # this command will print 'apple'
				  echo "${var%% *}"
				  
				  # This command will print 'orange'
				  echo "${var##* }"
				  ```
				- # Documentation
					- [SO Answer](https://stackoverflow.com/questions/16623835/remove-a-fixed-prefix-suffix-from-a-string-in-bash#16623897)
					- [puse bash bible](https://github.com/dylanaraps/pure-bash-bible)
					- <iframe width="560" height="315" src="https://www.youtube.com/embed/QXineadwG4E" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
			- # Text Replacement In Bash
			  collapsed:: true
				- Bash tip: instead of spawning an instance of `sed`, you can do text replacement in "pure" Bash like `status="${status//,/}"`. Breaking that down:
				- `status=`   # assign a new value to the Bash variable `status`.
				- `status="${ … }"` # I just always use double quotes when doing parameter (and command) substitution.
				- `status="${status … }"` # the new value I am assigning to `status` is the expansion of (value of) `status`, BUT first we alter that value…
				- `status="${status//PATTERN/STRING}"` # the `//` means "globally replace" (a single `/` would replace the first occurrence of PATTERN)
				-
				  ```shell
				  status="${status//,/}"
				  status="${status//PATTERN/STRING}"
				  
				  firstString="I love Suzi and Marry, but Suzi Most"
				  secondString="Sara"
				  echo "${firstString/Suzi/$secondString}"    # prints 'I love Sara and Marry'
				  ```
				- # Documentation
					- [pure bash bible](https://github.com/dylanaraps/pure-bash-bible)
			- # Text Case Modification In Bash
			  collapsed:: true
				- I realize that this is beside your point, but…don't shell out to `tr` like you did. It's really slow and Bash has built-in facilities for manipulating strings—especially case. Equivalent to your code `input=$(echo "$value" | tr '[:upper:]' '[:lower:]')` would be something like:
				- input="$*"
				- input="${input,,}"
				- We are assigning a new value to the `bash` variable `input`.  The right-hand-side of the `=` is the new value. If we used `${input}`, that would just be the value already in variable `input` The magic is in those two commas `,,`. A `,` operator after the variable name downcases the first letter of the variable and leaves the rest of the value unchanged. The double-comma `,,` operator after the variable downcases every character in the value.
				- You can use `^` and `^^` for uppercasing.
				- You could have done the same in a single line with `input="${*,,}"`
				- I ran the `tr` version as written above 1000 times and a "pure" Bash equivalent The `tr` version took 4.1 sec versus "pure" Bash's 0.04 sec (100 X faster).
					- See: https://gist.github.com/cfraizer/8f17c375837f6d904bcafd3adaa8466d for the code.
				- ## Parameter   What does it do?
				-
				  ```shell
				  ${VAR^}     # Uppercase first character.
				  ${VAR^^}    # Uppercase all characters.
				  ${VAR,}     # Lowercase first character.
				  ${VAR,,}    # Lowercase all characters.
				  ${VAR~}     # Reverse case of first character.
				  ${VAR~~}    # Reverse case of all characters.
				  ```
				  
				  ```shell
				  #!/usr/bin/env bash
				  
				  foo() {
				  local value="The Quick Brown FOX Jumped over The Lazy Dog."
				  
				  local -i loopCount=1000
				  local -i i=0
				  for (( i = 0; i < loopCount; ++i )); do
				    local newVal=""
				    newVal="${value,}"
				    printf "%s\n" "$newVal"
				  done
				  }
				  
				  
				  bar() {
				  local value="The Quick Brown FOX Jumped over The Lazy Dog."
				  
				  local -i loopCount=1000
				  local -i i=0
				  for (( i = 0; i < loopCount; ++i )); do
				    # shellcheck disable=SC2155
				    local newVal=$(echo "$value" | tr '[:upper:]' '[:lower:]')
				    printf "%s\n" "$newVal"
				  done
				  }
				  
				  baz() {
				  local value="$*"
				  
				  printf "%s\n" "${value,,}"
				  }
				  
				  foo
				  bar
				  baz
				  
				  # Lower Case Conversion
				  lower() {
				    # Usage: lower "string"
				    printf '%s\n' "${1,,}"
				  }
				  # Upper Case Conversion
				  upper() {
				    # Usage: upper "string"
				    printf '%s\n' "${1^^}"
				  }
				  # Reverse Case Conversion
				  reverse_case() {
				    # Usage: reverse_case "string"
				    printf '%s\n' "${1~~}"
				  }
				  ```
				- # Documentation
					- [pure bash bible](https://github.com/dylanaraps/pure-bash-bible)
			- # Text Blocks In Bash
			  collapsed:: true
				- You can have blocks of formatted text in a script for use such as a help menu If you want some of the text to be dynamic you will need to wrap it in double quote. Also echo CAN work for this but its just better to use `cat` or `printf`
				-
				  ```shell
				  cat <<EOF
				  Hello world
				  How's it going?
				  EOF
				  # Or use printf (also efficient, printf is built-in):
				  printf %s "\
				  Hello world
				  How's it going?
				  "
				  ```
				- # Documentation
					- <https://mywiki.wooledge.org/BashPitfalls>
		- **Bash Redirections**
		  collapsed:: true
			- When Bash starts, normally, 3 file descriptors are opened, 0, 1 and 2 also known as standard input (`stdin`), standard output (`stdout`) and standard error (`stderr`).
			-
			  | num  | val      |
			  | --- | ---     |
			  | 0    | `stdin`  |
			  | 1    | `stdout` |
			  | 2    | `stderr` |
			-
			  ```shell
			  2>/dev/null
			  ```
			- # Documentation
				- <https://wiki.bash-hackers.org/howto/redirection_tutorial>
		- **Exit Status In Bash**
		  collapsed:: true
			- You can check the exit status with the exit status variable:
			-
			  ```shell
			  echo "My script's exit status is '$?'"
			  ```
			- `$?` is only required if you need to retrieve the exact status of the previous command. If you only need to test for success or failure (any non-zero status), just test the command directly. e.g.:
			-
			  ```shell
			  if cmd; then
			    ...
			  fi
			  ```
				- # Documentation
					- <https://mywiki.wooledge.org/BashPitfalls>
	- ^^Data Types & Structs^^
	- ^^Flow Control^^
	  collapsed:: true
		- # Bash Test Conditionals
		  collapsed:: true
			- Testing conditions is down to using square bracket syntax:
			-
			  ```bash
			  if [ 1 = 3 ] || [ 2 = 2 ]; then
			    echo "yes!"
			  fi
			  ```
			- To note, double brackets are a BASH-ism and not POSIX compliant.
			  To test multiple conditions for the same evaluation do not use the
			  internal `-a` for and or the `-o` for or like:
			-
			  ```bash
			  if [ 1 = 3 -o 2 = 2 ]; then
			    echo "yes!"
			  fi
			  ```
			- Instead separate the tests into separate commands with the `&&` operator.
			  This way it will run each test as a separate command, AND it will only
			  continue forward if the condition is true:
			- `<this has to be true> && "AND" <this has to be true, to continue>`.
			- Double quote [[Bash Variables|variables]] use in the test condition unless you
			  explicitly know and understand why they should be unquoted.
			- ## Ternary Tests [pure bash bible](https://github.com/dylanaraps/pure-bash-bible)
				-
				  ```bash
				  # Ternary Tests
				  ## Set the value of var to var2 if var2 is greater than var.
				  ## var: variable to set.
				  ## var2>var: Condition to test.
				  ## ?var2: If the test succeeds.
				  ## :var: If the test fails.
				  ((var=var2>var?var2:var))
				  ```
			- # Documentation
				- <https://mywiki.wooledge.org/BashPitfalls>
		- # Bash IF Statements
		  collapsed:: true
			- Many beginners have an incorrect intuition about `if` statements brought about by seeing the very common pattern of an if keyword followed immediately by a `[` or `[[`. This convinces people that the `[` is somehow part of the `if` statement's syntax, just like parentheses used in C's if statement.
			- This is not the case! `if` takes a command. `[` is a command, not a syntax marker for the if statement. It's equivalent to the test command, except that the final argument must be a `]`. For example:
			-
			  ```bash
			  # POSIX
			  if [ false ]; then echo "HELP"; fi
			  if test false; then echo "HELP"; fi
			  ```
			- Are equivalent -- both checking that the argument "false" is non-empty. In both cases HELP will always be printed, to the surprise of programmers from other languages guessing about shell syntax.
			- The syntax of an if statement is:
			-
			  ```bash
			  if COMMANDS
			  then <COMMANDS>
			  elif <COMMANDS> # optional
			  then <COMMANDS>
			  else <COMMANDS> # optional
			  fi # required
			  ```
			- # Documentation
				- <https://mywiki.wooledge.org/BashPitfalls>
		- # Bash Case Statements
		  collapsed:: true
			- Case statement syntax in bash is a little strange but also really easy and they are very friendly and nice.
			- case will look for a value in a list of options, each option is appended with a paren then the commands that this option will run. these options can also expand with wild cards. To have a final catch all statement for anything that didnt meet a prior condition use `*` as the final case option.
			-
			  ```bash
			  case "$RESPONSE" in
			    n) exit ;;
			    N) exit ;;
			    q) exit ;;
			    Q) exit ;;
			    y) mkdir $DIR && touch $TEMPLATE_DECK && echo "category1:question1:answer1" >> $TEMPLATE_DECK && echo "category2:question2:answer2" >> $TEMPLATE_DECK && echo "category3:question3:answer3" >> $TEMPLATE_DECK && echo "$DIR_MADE_MSG" ;;
			    Y) mkdir $DIR && touch $TEMPLATE_DECK && echo "category1:question1:answer1" >> $TEMPLATE_DECK && echo "category2:question2:answer2" >> $TEMPLATE_DECK && echo "category3:question3:answer3" >> $TEMPLATE_DECK && echo "$DIR_MADE_MSG" ;;
			    *) echo "invalid choice, please select either 'y' or 'n'" ;;
			  esac
			  ```
		- # Loops In Bash
		  collapsed:: true
			- For looping over all positional arguments / words sent to the command you can use the following:
			-
			  ```bash
			  for arg in "$@"
			  # Or simply:
			  for arg
			  ```
			- Since looping over the positional parameters is such a common thing to do in
			  scripts, for arg defaults to for arg in `"$@"`. The double-quoted `"$@"` is
			  special magic that causes each parameter to be used as a single word (or a
			  single loop iteration). It's what you should be using at least 99% of the time.
			-
			  ```bash
			  # Correct version
			  
			  for x in "$@"; do
			  echo "parameter: '$x'"
			  done
			  
			  # or better:
			  
			  for x do
			  echo "parameter: '$x'"
			  done
			  
			  $ ./myscript 'arg 1' arg2 arg3
			  
			  #> parameter: 'arg 1'
			  #> parameter: 'arg2'
			  #> parameter: 'arg3'
			  ```
			-
			  ---
			-
			  ```bash
			  do [command list]; done
			  ```
			- This constitutes the actual loop that is used by the next few commands.
			  The list of commands between the do and done are the commands that will be executed in every iteration of the loop.
			-
			  ```bash
			  for [name] in [words]
			  ```
			- The next loop will iterate over each WORD after the in keyword.
			  The loop's commands will be executed with the value of the variable denoted by name set to the word.
			-
			  ```bash
			  for (( [arithmetic expression]; [arithmetic expression]; [arithmetic expression] ))
			  ```
			- The next loop will run as long as the second arithmetic expression remains true.
			  The first arithmetic expression will be run before the loop starts. The third arithmetic expression will be run after the last command in each iteration has been executed.
			-
			  ```bash
			  while [command list]
			  ```
			- The next loop will be repeated for as long as the last command ran in the command list exits successfully.
			-
			  ```bash
			  until [command list]
			  ```
			- The next loop will be repeated for as long as the last command ran in the command list exits unsuccessfully ("fails").
			-
			  ```bash
			  select [name] in [words]
			  ```
			- The next loop will repeat forever, letting the user choose between the given words.
			- The iteration's commands are executed with the variable denoted by name's value set to the word chosen by the user. Naturally, you can use break to end this loop.
			- # Documentation
				- <https://mywiki.wooledge.org/BashPitfalls>
	- ^^Functions^^
	  collapsed:: true
		- # Functions In Bash
		  collapsed:: true
			- [[Bash Variables|Variables]] assigned outside of functions can be overwritten in functions and display aberrant results if local isn't used.
			-
			  ```bash
			  foo="bar"
			  echo "top level: $foo"
			  
			  main(){
			    foo="func bar"
			    echo "func $foo"
			  }
			  main
			  echo "end $foo"
			  
			  # OUTPUT:
			  #> top level: bar
			  #> func func bar
			  #> end func bar
			  
			  #===#===#===#===#===#===#
			  
			  foo="bar"
			  echo "top level: $foo"
			  
			  main(){
			    local foo="func bar"
			    echo "func $foo"
			  }
			  main
			  echo "end $foo"
			  
			  # OUTPUT:
			  #> top level: bar
			  #> func func bar
			  #> end bar
			  ```
			- Do not use the function keyword, it reduces compatibility with older versions of bash.
			-
			  ```bash
			  # Right.
			  do_something() {
			    # ...
			  }
			  
			  # Wrong.
			  function do_something() {
			    # ...
			  }
			  ```
			-
			  ```bash
			  # Current function.
			  "${FUNCNAME[0]}"
			  
			  # Parent function.
			  "${FUNCNAME[1]}"
			  
			  # So on and so forth.
			  "${FUNCNAME[2]}"
			  "${FUNCNAME[3]}"
			  
			  # All functions including parents.
			  "${FUNCNAME[@]}"
			  ```
			- # Command Lists
			  collapsed:: true
				- `{ [command list]; }`
				- Execute the list of commands in the current shell as though they were one command.
				- Command grouping on its own isn't very useful. However, it comes into play wherever Bash syntax accepts only one command while you need to execute multiple.
				- For example, you may want to pass output of multiple commands via a pipe to another command's input:
				  ```bash
				  { ls .; ls ..; } | grep file-name
				  ```
				- Or you may want to execute multiple commands after a || operator:
				- ```bash
				  rm file || { echo "Removal failed, aborting."; exit 1; }
				  ```
				  - It is also used for [[Bash Functions|function]] bodies. Technically, this can also be used for loop bodies though this is undocumented, not portable and we normally prefer `do ...; done` for this):
				  - ```bash
				  for digit in 1 9 7; { echo "$digit"; }       # non-portable, undocumented, unsupported
				  - for digit in 1 9 7; do echo "$digit"; done   # preferred
				  ```
				- **\*Note**: You need a `;` before the closing `}` (or it must be on a new line).
				- Command Lists are similar but not identical to [[Bash Command Substitution]]
				- # Command Substitution
				  collapsed:: true
					- `( [command list] )`
					- Execute the list of commands in a subshell.
					- This is exactly the same thing as the command grouping above, only, the commands are executed in a subshell. Any code that affects the environment such as variable assignments, cd, export, etc. do not affect the main script's environment but are scoped within the brackets.
					- Note: You do not need a `;` before the closing `)`.
			- # Arithmetic Expansion
				- `(( [arithmetic expression] ))`
				- Evaluates the given expression in an arithmetic context.
				- That means, strings are considered names of integer variables, all operators are considered arithmetic operators (such as ++, \=\=, >, <=, etc..) ==You should always use this for performing tests on numbers!==
				- `$(( [arithmetic expression] ))`
				- Expands the result of the given expression in an arithmetic context.
				- This syntax is similar to the previous, but expands into the result of the expansion. We use it inside other commands when we want the result of the arithmetic expression to become part of another command.
	- ^^File Handling^^
	  collapsed:: true
		- # Using Temp Files With Bash
		  collapsed:: true
			- Temp files are stored in the `/tmp/` directory and will need to be removed upon script completion. Why use a temp file or directory? Because it will make it easier to have a storing place of a file that holds some information you want to be read, or just act as an intermediary file/directory.
			-
			  ```bash
			  #  Documentation
			  # All temp files need those X's for randomization
			  # check out `man mktemp` for more details
			  tmpfile=$(mktemp /tmp/abc-script.XXXXXX)
			  
			  # <CODE>
			  
			  rm "$tmpfile"
			  ```
			- # Documentation
				- [SO answer](https://unix.stackexchange.com/questions/181937/how-create-a-temporary-file-in-shell-script)
	- ^^Tips, Tricks, & Hacks^^
	  collapsed:: true
		- `printf`
		  collapsed:: true
			- # The printf Builtin
			  
			  Instead of using `ls -l <pattern>` to return a wildcard glob, use the wildcard as it is and avoid `ls`
			  
			  
			  ```bash
			  #  Documentation
			  pattern="ex*"
			  
			  printf '%s\n' $pattern   # not ``ls -1 $pattern''
			  # > file1.txt
			  # > file_other.txt
			  
			  for file in $pattern; do  # definitely, definitely not ``for file in $(ls $pattern)''
			    printf 'Found file: %s\n' "$file"
			  done
			  # > Found file: file1.txt
			  # > Found file: file_other.txt
			  ```
			- # Documentation
			  
			  [parsing file globs with ls](https://mywiki.wooledge.org/ParsingLs)
		- `Colorized Output In Bash`
		  collapsed:: true
			- Using ANSI escape codes you can make your terminal display colored output
			  
			  | Color        | Code         | Color        | Code         |
			  | :-:          | :-:          | :-:          | :-:          |
			  | Black        | '\033[0;30m' | Dark Gray    | '\033[1;30m' |
			  | Red          | '\033[0;31m' | Light Red    | '\033[1;31m' |
			  | Green        | '\033[0;32m' | Light Green  | '\033[1;32m' |
			  | Brown/Orange | '\033[0;33m' | Yellow       | '\033[1;33m' |
			  | Blue         | '\033[0;34m' | Light Blue   | '\033[1;34m' |
			  | Purple       | '\033[0;35m' | Light Purple | '\033[1;35m' |
			  | Cyan         | '\033[0;36m' | Light Cyan   | '\033[1;36m' |
			  | Light Gray   | '\033[0;37m' | White        | '\033[1;37m' |
			- `RED='\033[0;31m'`
			- 30-37 sets foreground color
			- 40-47 sets background color
			-
			  ```bash
			  RED='\033[0;31m'
			  NC='\033[0m'
			  
			  echo -e "${LRED}Hard${NC} [1]   ${RED}Difficult${NC} [2]   ${YELLOW}Normal${NC} [3]   ${GREEN}Mild${NC} [4]   ${LGREEN}Easy${NC} [5]"
			  ```
			- # Documentation
				- [SO answer](https://stackoverflow.com/questions/5947742/how-to-change-the-output-color-of-echo-in-linux#5947802)
				- [more documentation](https://misc.flogisoft.com/bash/tip_colors_and_formatting)
		- `get opts`
		  collapsed:: true
			- # Get Opts In Bash
			  
			  how to get flag options in a bash script
			  
			  ```bash
			  #  Documentation
			  a_flag=''
			  b_flag=''
			  files=''
			  verbose='false'
			  
			  print_usage() {
			  printf "Usage: ..."
			  }
			  
			  while getopts 'abf:v' flag; do
			  case "${flag}" in
			    a) a_flag='true' ;;
			    b) b_flag='true' ;;
			    f) files="${OPTARG}" ;;
			    v) verbose='true' ;;
			    *) print_usage
			       exit 1 ;;
			  esac
			  done
			  ```
			- # Documentation
				- [SO Article](https://stackoverflow.com/questions/7069682/how-to-get-arguments-with-flags-in-bash#21128172)
		-