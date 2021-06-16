# **Workflow**
	- Make a new Git Repo
	- [[VSCode]] [[gitignore]] extension to add Python gitignore
	- add [[gitattributes]] file
	- Add config files for terminal/[[VSCode]]/Extensions
	- Setup Linting CI/CD with the `github super linter`
		- Super linter file
			-
			  ```yaml
			  
			  ```
		- [[black]] with a `.python-black` config file
		- [[flake8]] with a `.flake8` file
			-
			  ```
			  [flake8]
			  max-line-length = 88
			  max-complexity = 18
			  select = B,C,E,F,W,T4,B9
			  ignore = E203, E266, E501, W503, F403, F401
			  ```
		- [[isort]] with a `.isort.cfg` file
			-
			  ```
			  [settings]
			  line_length = 88
			  multi_line_output = 3
			  include_trailing_comma = True
			  known_third_party = 
			  ```
	- setup repo branch policies and settings
	- [[Python Poetry]] setup
		- `poetry new <PROJECT>` or `poetry init`
		- `poetry shell`
		- `poetry add black flake8 isort pre-commit`
		- setup pre-commit hooks for formatting
			- `poetry run pre-commit install`
			- `poetry run pre-commit autoupdate`
			- make pre-commit file
				-
				  ```yaml
				  repos:
				    -   repo: https://github.com/asottile/seed-isort-config
				        rev: v1.9.3
				        hooks:
				        - id: seed-isort-config
				    -   repo: https://github.com/pre-commit/mirrors-isort
				        rev: v4.3.21
				        hooks:
				        - id: isort
				    - repo: https://github.com/psf/black
				      rev: 21.6b0
				      hooks:
				      - id: black
				        language_version: python3
				        description: "Black: The uncompromising Python code formatter"
				    -   repo: https://gitlab.com/pycqa/flake8
				        rev: 3.9.2
				        hooks:
				        - id: flake8
				  ```
		-
-
- **Old Workflow**
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
	- _Architecture_
		- setup the [[black]] config file pre-commit hook
			- [Pre-Commit](https://pre-commit.com/) Hooks
	- _Ending_
		- `deactivate`
			- deactivate virtual environment