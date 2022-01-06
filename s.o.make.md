---
id: dfEx7EDWYxzUSCiIVbbQP
title: Make
desc: ''
updated: 1641267479000
created: 1641105063857
stub: false
isDir: false
---

- **Resources**
  - [What is a Makefile and how does it work?](https://opensource.com/article/18/8/what-how-makefile)
  - [C++ Programming Tutorial 75 - Creating a Simple Makefile](https://youtu.be/6Gw1rNyTJWA)
  - [makefiles: the problem](https://calmcode.io/makefiles/the-problem.html)
  - [How To Manage Your Dotfiles With Make](https://youtu.be/aP8eggU2CaU)
  - [How To Write a Makefile](https://youtu.be/TQ7SyYyKXhk)
  - <https://www.gnu.org/software/make/manual/make.html>
- **Installation on Windows**
  - Install from [Here](http://gnuwin32.sourceforge.net/packages/make.htm)
  - Run `C:\MinGW\bin\mingw-get.exe` to install the Make tools
  - Add `C:\MinGW\bin` to your `$PATH`
  - make [[PowerShell|import.powershell]] alias of `mingw32-make.exe` to `make`

```powershell
New-Alias -Name make -Value mingw32-make.exe
```

- **Specifying dependency targets**

```make
final_target: sub_target final_target.c
	Recipe_to_create_final_target

sub_target: sub_target.c
	Recipe_to_create_sub_target
```

```make
say_hello:
	echo "Hello World"
```

- `say_hello:` == _The Target_
- _prerequisites_ or _dependencies_ follow the target
- `echo "Hello World"` == _The Recipe_
- The _target_, _prerequisites_, and _recipes_ together make a _rule_.
-
- **Suppress command** text and only show output with `@` like `@echo "hello world"`

```make
say_hello:
	  @echo "Hello World"

generate:
	  @echo "Creating empty text files..."
	  touch file-{1..10}.txt

clean:
	  @echo "Cleaning up..."
	  rm *.txt
```

- This will only run the `say_hello` function because it's the default target ( the first thing )
- to hard code the default target, include this at beginning of file: `.DEFAULT_GOAL := generate`
  - To instead run all targets the target `all` is used to call all other targets

```make
all: say_hello generate

say_hello:
	  @echo "Hello World"

generate:
	  @echo "Creating empty text files..."
	  touch file-{1..10}.txt

clean:
	  @echo "Cleaning up..."
	  rm *.txt
```

- **Variable a.k.a. Macros** are like variable replacement in makefiles

```make
# ==================
# USING VARIABLES (aka macros)
# ==================
# VARIABLENAME = VALUE OF VARIABLE
# they expand using the syntax $(VARIABLENAME)


TMP = tester1.txt
OUTPUT = tester2.txt

$(OUTPUT): $(TMP)
cat $(TMP) > $(OUTPUT)

$(TMP):
echo "this is a test" > $(TMP)
```

- **Inference rules**

```make
# ==================
# USING INFERENCE RULES
# ==================

# $@ = prod.txt (if out of date)
# $* = prod (its the target with the .extention removed)
# $< = dep.txt (aka its the first dependancy)

# .SUFFIXES appends these to suffixes used for inference rules

.SUFFIXES: .tmp .txt

all: tester.txt

# make a .txt file using a .tmp file
# $< for the .tmp file
# $@ for the .txt file

# .inextension.outextension:
.tmp.txt:
cat $< > $*
```
