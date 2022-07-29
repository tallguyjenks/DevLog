

**Using Poetry**

- 1. [Installation](https://python-poetry.org/docs/#windows-powershell-install-instructions)
  - 1.1 Configuration: `poetry completions bash > /etc/bash_completion.d/poetry.bash-completion`
- 2. Usage `poetry new poetry-demo` to make a new directory project or `poetry init` in current project
- 3. Activate venv in the project `poetry shell`
- 4. Add dependencies `poetry add pandas` add developer dependencies with `poetry add --dev pytest`
  - 4.1 get latest versions of all dependencies `poetry update` or list which to update `poetry update pandas`
- 5. Build the source and wheel archives `poetry build`
- 6. deactivate venv `exit`
- 7. [publish to PyPi](https://python-poetry.org/docs/libraries/#publishing-to-pypi) `poetry publish`
- Opening a poetry project and installing them `poetry install`
- update poetry `poetry self update`
- poetry help pages easy to access `poetry help <command>`
