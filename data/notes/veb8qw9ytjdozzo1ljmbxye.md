

- [Calm Code](https://calmcode.io/black/introduction.html)
- `.pre-commit-config.yaml`

```yml
repos:
-   repo: https://github.com/asottile/seed-isort-config
	rev: v2.2.0
	hooks:
	- id: seed-isort-config
-   repo: https://github.com/pre-commit/mirrors-isort
	rev: v5.8.0
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
-   repo: https://github.com/pre-commit/pre-commit-hooks
	rev: v4.0.1
	hooks:
	-   id: trailing-whitespace
	-   id: end-of-file-fixer
	-   id: check-docstring-first
	-   id: check-json
		exclude: .vscode/settings.json
	-   id: check-added-large-files
	-   id: check-yaml
	-   id: debug-statements
	-   id: name-tests-test
	-   id: requirements-txt-fixer

```

- This will run all of the hooks before every commit ensuring code quality

---

- Reference:
  - [[s.l.python.libs.pre-commit]]
- Related:
  - [[s.l.python.libs.venv.vulture]]
  - [[cli.cmd.git]]

