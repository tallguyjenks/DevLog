---
tags: 
alias: command line, command line interface
---

- ^^Resources^^
	- [Command Line Interface Guidelines](https://clig.dev/)
- ^^Related^^
	- [[Bash]]
	- [[C++]]
	- [[Clang]]
- ^^Philosophy^^
  collapsed:: true
	- **Human-first design**
	- **Simple parts that work together**
	- **Consistency across programs**
	- **Saying (just) enough**
	- **Ease of discovery**
	- **Conversation as the norm**
	- **Robustness**
	- **Empathy**
	- **Chaos**
- ^^Guidelines^^
	- **The Basics**
	  collapsed:: true
		- _Use a command-line argument parsing library where you can._
			- Go: Cobra, cli
			  Java: picocli
			  Node: oclif
			  PHP: console
			  Python: [[click]], Typer, [[argparse]]
			  Ruby: TTY
			  Rust: clap, structopt
			  Swift: swift-argument-parser
		- *Return zero exit code on success, non-zero on failure*
		- _Send output to stdout._
		- _Send messaging to stderr._
	- **Help**
	  collapsed:: true
		- _Display help text when passed no options, the -h flag, or the --help flag._
		- _Display a concise help text by default._
		- _Show full help when -h and --help is passed._
		- _Provide a support path for feedback and issues._
		- _In help text, link to the web version of the documentation._
		- _Lead with examples._
		- _If you’ve got loads of examples, put them somewhere else_
		- _Display the most common flags and commands at the start of the help text._
		- _Use formatting in your help text._
		- _If the user did something wrong and you can guess what they meant, suggest it._
		- _If your command is expecting to have something piped to it and stdin is an interactive terminal, display help immediately and quit._
	- **Documentation**
	  collapsed:: true
		- _Provide web-based documentation._
		- _Provide terminal-based documentation._
		- _Consider providing man pages._
	- **Output**
	  collapsed:: true
		- _Human-readable output is paramount._
		- _Have machine-readable output where it does not impact usability_
		- _If human-readable output breaks machine-readable output, use --plain to display output in plain, tabular text format for integration with tools like [[grep]] or [[awk]]._
		- _Display output as formatted [[JSON]] if --json is passed._
		- _Display output on success, but keep it brief._
		- _If you change state, tell the user._
		- _Make it easy to see the current state of the system._
		- _Suggest commands the user should run._
		- _Actions crossing the boundary of the program’s internal world should usually be explicit._
		- _Increase information density—with ASCII art!_
		- _Use color with intention._
		- _Disable color if your program is not in a terminal or the user requested it._
			- `stdout` or `stderr` is not an interactive terminal (a TTY). It’s best to individually check—if you’re piping `stdout` to another program, it’s still useful to get colors on stderr.
			  The `NO_COLOR` environment variable is set.
			  The `TERM` environment variable has the value `dumb`.
			  The user passes the option `--no-color`.
			  You may also want to add a `MYAPP_NO_COLOR` environment variable in case users want to disable color specifically for your program.
		- _If stdout is not an interactive terminal, don’t display any animations._
		- _Use symbols and emoji where it makes things clearer._
		- _By default, don’t output information that’s only understandable by the creators of the software._
		- _Don’t treat `stderr` like a log file, at least not by default._
		- _Use a pager (e.g. `less`) if you are outputting a lot of text._
			- [[pypager]] in [[python]]
	- **Errors**
		-
	- **Arguments and flags**
	- **Interactivity**
	- **Subcommands**
	- **Robustness**
	- **Future-proofing**
	- **Signals and control characters**
	- **Configuration**
	- **Environment variables**
	- **Naming**
	- **Distribution**
	- **Analytics**