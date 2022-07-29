
- [[s.q.tsql]] Comparing Sub queries and CTE's there's no real difference.
  - CTE's care recursive whereas sub queries are not
  - CTE's only live for the duration of the execution. If you need that data for multiple queries and it is used in multiple places then you're likely better off using temporary tables.

```sql
WITH myFirstCTE
AS
(
	SELECT * 
	FROM BOA_BAICodes
), mySecondCTE
AS
(
	SELECT TOP 100 *
	FROM myFirstCTE
	WHERE BAI_Code > 100
)
	SELECT SUM(CAST(BAI_CODE AS INT)) AS mySum
	FROM mySecondCTE
	WHERE BAI_Code > 200
```

```bash
git notes add -m 'Tested-by: Johannes Sixt <j6t@kdbg.org>' 72a144e2
git show -s 72a144e
#> [...]
#>    Signed-off-by: Junio C Hamano <gitster@pobox.com>
#>
#> Notes:
#>    Tested-by: Johannes Sixt <j6t@kdbg.org>
```

- Add notes to particular commits and then show them afterwards

	- Git hooks
		- Basically they're triggers that run on certain commands and execute scripts
		- [Getting started with git hooks](https://medium.com/@f3igao/get-started-with-git-hooks-5a489725c639)
		- [git hooks](https://pypi.org/project/git-pre-commit-hook/) 
		- [More python git hooks](https://www.omerkatz.com/blog/2013/5/23/git-hooks-part-2-implementing-git-hooks-using-python) 
		- [even more](https://pre-commit.com/)
		-  [awesome git hooks](https://github.com/aitemr/awesome-git-hooks)
		-  azure devops [Branch policies](https://docs.microsoft.com/en-us/azure/devops/repos/git/branch-policies?view=azure-devops) are kind of like hard stop checklist items like a merge conflict to be resolved before merge
    - [[s.apps.azure.devops]] Pipelines like [[cli.cmd.git.tools.github.github-actions]] are automated [[terms.ci-cd]] tools driven by [[s.df.yaml]] files. This is the pipeline for a super linter:

```yaml
# Starter pipeline
# Start with a minimal pipeline that you can customize to build and deploy your code.
# Add steps that build, run tests, deploy, and more:
# https://aka.ms/yaml
		
# This code src: https://www.meziantou.net/running-github-super-linter-in-azure-pipelines.html
# referenced docker container script: https://github.com/github/super-linter
trigger:
- '*'
		
# Use multiple jobs, so the linter can work in parallel to the build.
# This also allows to run the Linter on Linux whereas you build can run on Windows or Mac.
jobs:
- job: lint
pool:
vmImage: 'ubuntu-20.04'
steps:
- script: docker pull github/super-linter:latest
	displayName: Pull GitHub Super-Linter image
- script: >-
	docker run \
	-e RUN_LOCAL=true \
	-v $(System.DefaultWorkingDirectory):/tmp/lint \
	github/super-linter
displayName: 'Run GitHub Super-Linter'
```

- This pipeline will run the same Markdown Lint as the [[s.apps.vscode]] extension, sample [config file here](https://github.com/github/super-linter/blob/master/TEMPLATES/.markdown-lint.yml)
- [Link to the super linter yaml file](https://www.meziantou.net/running-github-super-linter-in-azure-pipelines.htm)
- [In two separate places for source material](https://blog.tyang.org/2020/06/27/use-github-super-linter-in-azure-pipelines/)
