---
title: Lisp
---

## **Language**
### ^^Setup^^
#### VS Code Extensions
#### `ailisp.strict-paredit`
#### `ailisp.commonlisp-vscode`
##### `mattn.lisp`
##### `ailisp.commonlisp-vscode`
##### `ailisp.strict-paredit`
#### `ailisp.commonlisp-vscode`
##### `mattn.lisp`
#### MacOS Boostrap
##### 
```bash
brew install clisp
brew install roswell
ros install ailisp/linedit
ros install ailisp/prepl
ros install ailisp/cl-lsp
ros install sbcl
ros use sbcl
```
### ^^Resources^^
#### https://opensource.com/article/21/5/learn-lisp
#### https://learnxinyminutes.com/docs/common-lisp/
### ^^Syntax^^
#### One of the hallmarks of lisp is that the data resembles the code.
#### Parens. Parens everywhere.
#####
```lisp
(+ 1 2)
;; 3
```
#### Variables
#####
```lisp
(setf foo "hello world")
(pprint foo)
;; hello world
```
##### 
```lisp
(pprint (string-upcase foo))
;; HELLO WORLD
```
### ^^Data Types & Structs^^
### ^^Flow Control^^
### ^^Functions^^
#### Using functions
##### pretty print function:
######
```lisp
(pprint "hello world")
```
#### Create Functions
##### 
```lisp
(defun myPrinter (s) (pprint s))
(myPrinter "Hello World")
;; Hello World
```
### ^^File Handling^^
### ^^Tips, Tricks, & Hacks^^
### ^^Libraries^^
### ^^Projects^^

##