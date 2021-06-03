---
title: Python
tags: language
---

-
  > Python is the most powerful language you can still read.
  > \
  > \- Paul Dubois
- **Language**
	- ^^Setup^^
	- ^^Resources^^
	- TODO [Comprehensive Cheatsheet](https://github.com/gto76/python-cheatsheet)
	  todo:: 1620885582093
	- TODO [article on logging for a python app](https://towardsdatascience.com/the-reusable-python-logging-template-for-all-your-data-science-apps-551697c8540)
	  todo:: 1620885579117
	- TODO [thomas-cokelaer python notes](https://thomas-cokelaer.info/tutorials/python/index.html)
	  todo:: 1620885575348
	- TODO [perceptilabs](https://www.perceptilabs.com/papers)
	  todo:: 1620885568483
	- ^^Projects^^
	- ^^Tools^^
	- [[Jupyter]]
	- [[Kite]]
	- **Dependency Management** [[Python Poetry]] [[pydeps]]
	- [[VSCode]] Extensions
		- _General_
			- `ms-python.python` Python language support
			- `ms-python.vscode-pylance` Python language support
			- `brainfit.vscode-importmagic` Fix missing module imports
			- `formulahendry.code-runner` Code runner to run the language for output and not just python code
			- _AI Code Completion_
				- [Comparisons here](https://medium.com/swlh/kite-vs-tabnine-which-ai-code-autocomplete-should-you-choose-eb6eba85c3a6)
					- ❌️ `kiteco.kite` Kite
					- ✅️ `tabnine.tabnine-vscode` TabNine
			- `almenon.arepl` Coding REPL
		- _Documentation_
			- `njpwerner.autodocstring` Auto Generatre Doc Strings
		- _Formatting_
			- `kevinrose.vsc-python-indent` Correct Indentation
		- _Debugging_
			- `dongli.python-preview` Preview execution stack
		- _Unit Testing_
			- `littlefoxteam.vscode-python-test-adapter` Python Test explorer
		- _Static Typing_
			- `njqdev.vscode-python-typehint` Data type hint
			- `ms-pyright.pyright` for static type checking
		- _App Dev_
			- ❌️ `nikolapaunovic.tkinter-snippets` [[tkinter]] snippets
			- `njqdev.vscode-python-typehint` Data type hint
		- _Jupyter Notebooks_
			- `jithurjacob.nbpreviewer` Jupyter Notebook Support and Viewing
			- `ms-toolsai.jupyter` Jupyter Notebook Support and Viewing
-
  ---
- **Workflow**
	- _Starting_
		- `python3 -m venv projects/env_name`
			- create virtual environment
		- `source project_env/bin/activate`
			- activate virtual environment
		- `which python`
			- confirm usage
		- install necessary packages
		- `pip freeze  requirements.txt`
			- snap shot of requirements for reproduce-ability with
		- `pip install -r requrirements.txt`
			- to import requirements from elsewhere
	- _Ending_
		- `deactivate`
			- deactivate virtual environment