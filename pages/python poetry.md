---
title: Python Poetry
tags: tools
---

- DONE [[Python]] https://python.plainenglish.io/start-managing-your-dependencies-using-poetry-in-python-b2f1e227fcf7
  todo:: 1620835281994
  done:: 1623440773502
- **Using Poetry**
	-
	  1. [Installation](https://python-poetry.org/docs/#windows-powershell-install-instructions)
		- 1.1 Configuration: `poetry completions bash > /etc/bash_completion.d/poetry.bash-completion`
	-
	  2. Usage `poetry new poetry-demo`
	-
	  3. Activate venv in the project `poetry shell`
	-
	  4. Add dependencies `poetry add pandas`
		- 4.1 get latest versions of all dependencies `poetry update` or list which to update `poetry update pandas`
	-
	  5. Build the source and wheel archives `poetry build`
	-
	  6. deactivate venv `exit`
	-
	  7. [publish to PyPi](https://python-poetry.org/docs/libraries/#publishing-to-pypi) `poetry publish`
-
  ---
- Opening a poetry project and installing them `poetry install`
- update poetry `poetry self update`
-