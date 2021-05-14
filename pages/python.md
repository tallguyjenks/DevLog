---
title: Python
tags: language
---

## 
> Python is the "most powerful language you can still read.
> \
> \- Paul Dubois
## **Language**
#### ^^Setup^^
### ^^Resources^^
#### TODO [Comprehensive Cheatsheet](https://github.com/gto76/python-cheatsheet)
:PROPERTIES:
:todo: 1620885582093
:END:
#### TODO [article on logging for a python app](https://towardsdatascience.com/the-reusable-python-logging-template-for-all-your-data-science-apps-551697c8540)
:PROPERTIES:
:todo: 1620885579117
:END:
#### TODO [thomas-cokelaer python notes](https://thomas-cokelaer.info/tutorials/python/index.html)
:PROPERTIES:
:todo: 1620885575348
:END:
#### TODO [perceptilabs](https://www.perceptilabs.com/papers)
:PROPERTIES:
:todo: 1620885568483
:END:
### ^^Projects^^
### ^^Tools^^
#### [[Jupyter]]
#### [[Kite]]
#### **Dependency Management** [[Python Poetry]] [[pydeps]]
####
### ^^Libraries^^
#### **Utils:** [[pyinstaller]]
#### **Benchmarking:** [[clockpy]]
#### **Unit Testing:** [[unittest]]
#### **Logging:** [[logging]]
#### **Virtual Environment:** [[venv]]
#### **tkinter**
### ^^Syntax^^
#### **Conventions**
##### TODO check PEP for style conventions
:PROPERTIES:
:todo: 1620898933798
:END:
##### Use uppercase initials for class names, lowercase for all others.
###### function names all in lowercase
###### `class.object.field` names should not be capitalized, and if multiple words used, then separate with underscores:
####### `user1.first_name` > `user1.firstName`
##### Name a private identifier with a leading underscore ( `_username`)
##### Name a strongly private identifier with two leading underscores (`__password`)
##### Special identifiers in Python end with two leading underscores.
###### _A.K.A. Dunder methods (double under-score)_ `__MAIN__`
#### **Decorators**
##### TODO [Decorators 101](https://sureshdsk.dev/python-decorators-101)
:PROPERTIES:
:todo: 1620835767488
:END:
##### TODO [Decorators 201](https://sureshdsk.dev/python-decorators-201)
:PROPERTIES:
:todo: 1620835782488
:END:
##### TODO [Decorators with params](https://sureshdsk.dev/python-decorators-with-parameters)
:PROPERTIES:
:todo: 1620835794488
:END:
### ^^Data Types & Structs^^
### ^^Flow Control^^
### ^^Functions^^
### ^^File Handling^^
### ^^Tips, Tricks, & Hacks^^
## 
---
## **Workflow**
### _Starting_
#### `python3 -m venv projects/env_name`
##### create virtual environment
#### `source project_env/bin/activate`
##### activate virtual environment
#### `which python`
##### confirm usage
#### install necessary packages
#### `pip freeze  requirements.txt`
##### snap shot of requirements for reproduce-ability with
#### `pip install -r requrirements.txt`
##### to import requirements from elsewhere
### _Ending_
#### `deactivate`
##### deactivate virtual environment
