

## Workflow

- Make a new Git Repo
- vscode gitignore extension to add Python gitignore
- add gitattributes file
- Add config files for terminal/vscode/Extensions
- Setup Linting CI/CD with the `github super linter`
  - Super linter file

```yaml
# https://aka.ms/yaml
# Initial code src: https://www.meziantou.net/running-github-super-linter-in-azure-pipelines.htm
# referenced docker container script: https://github.com/github/super-linter
# Official MS Documentation: https://docs.microsoft.com/en-us/azure/devops/pipelines/?view=azure-devops
# YAML Schema Info: https://docs.microsoft.com/en-us/azure/devops/pipelines/yaml-schema?view=azure-devops&tabs=schema%2Cparameter-schema
#============================================================================================================#
name: 'Super Linter -- $(Date:yyyyMMdd)$(Rev:.r)' #............................# Name of the Job Instance When Ran
trigger: #.....................................................................# What triggers the job to run?
- '*' #........................................................................# Everything triggers it
variables: #...................................................................# Variables for any parameter testing or changes
default_branch: 'prod' #.....................................................# What Branch is the default branch to run the job on
log_level: 'WARN' #..........................................................# What level and above of notices do you want to receive? WARN & ERROR
excluded_paths: '.*(\.github|\.vscode).*' #..................................# What Locations are ignored by this job?
jobs: #........................................................................# No stages so top level list of jobs to run
- job: 'super_linter' #......................................................# Name of the job
  #pool: 'default' #.........................................................# The Agent Pool if we wanted to use our self hosted option
  pool: #....................................................................# Which Agent Pool runs the job?
	vmImage: 'ubuntu-latest' #...............................................# Microsoft Hosted Image to Run Job on
  steps: #...................................................................# The list of steps that make up the job
  - script: 'docker pull github/super-linter:latest' #.......................# Commands to Run in the default shell of the host machine See VmImage
	displayName: 'Pull GitHub Super-Linter image' #..........................# Display name of this step when it executed in the pipeline
  - script: >-
	  docker run \
		-e IGNORE_GITIGNORED_FILES=true \
		-e MARKDOWN_CONFIG_FILE=.markdownlint.jsonc \
		-e JAVASCRIPT_ES_CONFIG_FILE=.eslintrc.json \
		-e PYTHON_BLACK_CONFIG_FILE=.python-black \
		-e PYTHON_FLAKE8_CONFIG_FILE=.flake8 \
		-e PYTHON_ISORT_CONFIG_FILE=.isort.cfg \
		-e DEFAULT_BRANCH=$(default_branch) \
		-e LOG_LEVEL=$(log_level) \
		-e FILTER_REGEX_EXCLUDE='$(excluded_paths)' \
		-e RUN_LOCAL=true \
		-v $(System.DefaultWorkingDirectory):/tmp/lint github/super-linter
# - script: >- #...............................................................# The Below is the multi-line inline script ran in the default shell formatted for legibility
#     docker run \ #...........................................................# Running the docker image with the following commands `-e` is enviornmental variable `-v` is the volume to attach to (a file path)
#       -e IGNORE_GITIGNORED_FILES=true \ #....................................# BOOL Variable asking if the job should lint .gitignored files
#       -e MARKDOWN_CONFIG_FILE=.markdownlint.jsonc \ #........................# STRING Variable of Markdown config file
#       -e JAVASCRIPT_ES_CONFIG_FILE=.eslintrc.json \ #........................# STRING Variable of JSON config file
#       -e PYTHON_BLACK_CONFIG_FILE=.python-black \ #..........................# STRING Variable of Python Black config file
#       -e PYTHON_FLAKE8_CONFIG_FILE=.flake8 \ #...............................# STRING Variable of Python flake8 config file
#       -e PYTHON_ISORT_CONFIG_FILE=.isort.cfg \ #.............................# STRING Variable of Python isort config file
#       -e DEFAULT_BRANCH=$(default_branch) \ #................................# STRING Variable of default branch to run job on when not targeted manually
#       -e LOG_LEVEL=$(log_level) \ #..........................................# STRING Variable of desired log output level
#       -e FILTER_REGEX_EXCLUDE=$(excluded_paths) \ #..........................# STRING Variable of regex path list to ignore for the job
#       -e RUN_LOCAL=true \ #..................................................# BOOL Variable to Run the container locally (On VmImage)
#       -v $(System.DefaultWorkingDirectory):/tmp/lint github/super-linter #...# Volume to attach to
	displayName: 'Run GitHub Super-Linter' #.................................# Name of this step in the job
```

- [[black]] with a `pyproject.toml` addition

```toml
[tool.black]
line-length = 88
include = '\.pyi?
exclude = '''
/(
\.git
| \.hg
| \.mypy_cache
| \.tox
| \.venv
| _build
| buck-out
| build
| dist
| docs
| notes
)/
'''
```

- [[s.l.python.libs.flake8]] with a `.flake8` file

```
[flake8]
max-line-length = 88
max-complexity = 18
exclude =
.git,
__pycache__,
build,
dist
select = B,C,E,F,W,T4,B9
ignore =
E203, # E203: whitespace before ‘:’
E266, # E266: too many leading ‘#’ for block comment
E501, # E501: line too long (82 > 79 characters)
W503, # W503: line break before binary operator
F401, # F401: module imported but unused
F403  # F403: ‘from module import *’ used; unable to detect undefined names

```

- [[s.l.python.libs.isort]] with a `pyproject.toml` addition

```toml
[tool.isort]
line_length = 88
multi_line_output = 3
include_trailing_comma = true
skip_glob = []
known_third_party = []
```

- [[s.l.python.libs.venv.vulture]] with a `pyproject.toml` addition

```toml
[tool.vulture]
exclude = []
ignore_decorators = ["@app.route", "@require_*"]
ignore_names = []
make_whitelist = true
min_confidence = 80
paths = ["src/"]
sort_by_size = true
verbose = false
```

- setup repo branch policies and settings
- [[s.l.python.build.poetry]] setup
  - `poetry new <PROJECT>` or `poetry init`
  - Spin up virtual environment `poetry shell`
  - `poetry add --dev pre-commit pytest pytest-cov`
  - setup pre-commit hooks for formatting
  - make `.pre-commit-config.yaml` file
  - `poetry run pre-commit install`
  - `poetry run pre-commit autoupdate`
  - `poetry run pre-commit run` (to test that it works)

```yaml
repos:
- repo: https://github.com/asottile/seed-isort-config
  rev: v2.2.0
  hooks:
  - id: seed-isort-config
- repo: https://github.com/pre-commit/mirrors-isort
  rev: v5.8.0
  hooks:
  - id: isort
- repo: https://github.com/psf/black
  rev: 21.6b0
  hooks:
  - id: black
	language_version: python3
	description: "Black: The uncompromising Python code formatter"
- repo: https://gitlab.com/pycqa/flake8
  rev: 3.9.2
  hooks:
  - id: flake8
- repo: https://github.com/jendrikseipp/vulture
  rev: 'v2.3'
  hooks:
  - id: vulture
- repo: https://github.com/pre-commit/pre-commit-hooks
  rev: v4.0.1
  hooks:
  - id: trailing-whitespace
	log_file: src/logs/hooks.log
  - id: end-of-file-fixer
	log_file: src/logs/hooks.log
  - id: check-docstring-first
	log_file: src/logs/hooks.log
  - id: requirements-txt-fixer
	log_file: src/logs/hooks.log
  - id: check-added-large-files
	log_file: src/logs/hooks.log
  - id: check-json
	log_file: src/logs/hooks.log
	exclude: .vscode/settings.json
  - id: check-yaml
	log_file: src/logs/hooks.log
  - id: check-toml
	log_file: src/logs/hooks.log
  - id: check-xml
	log_file: src/logs/hooks.log
  - id: debug-statements
	log_file: src/logs/hooks.log
  - id: name-tests-test
	log_file: src/logs/hooks.log
  - id: check-shebang-scripts-are-executable
	log_file: src/logs/hooks.log
  - id: check-merge-conflict
	log_file: src/logs/hooks.log
  - id: check-symlinks
	log_file: src/logs/hooks.log
  - id: destroyed-symlinks
	log_file: src/logs/hooks.log
  - id: debug-statements
	log_file: src/logs/hooks.log
  - id: detect-private-key
	log_file: src/logs/hooks.log
  - id: no-commit-to-branch
	log_file: src/logs/hooks.log
	args: [--branch, prod]

```

- Set up logging and this directory structure to start:

```
.
├───.github
│   ├───ISSUE_TEMPLATE
│   ├───linters
│   └───workflows
├───doc
└───src
  ├───logger
  │	├───__init__.py
  │   └───logger.py
  ├───logs
  ├───mypackage
  │ 	├───__init__.py
  │   └───mypackage.py
  └───app.py
```

- Set up unit testing framework with [[s.l.python.libs.pytest]]
  - `pytest-cov --cov <SRC DIR> --cov-report html`
    - This tests the coverage of the entire source code directory and writes an intricate [[s.m.html]] report for viewing test results
- Set up auto documentation with [[s.l.python.libs.sphinx]] & [[s.m.restructured-text]]
- **More on Packaging**
  - build your distribution: `poetry build`
  - publish your distribution: `poetry publish`
- **Opening someone elses poetry project**
  - install dependencies `poetry install`
