

- [[s.l.r]] [[s.l.r.tools.rmarkdown]]
  - [[s.l.r.libs.slidev]] [Website](https://sli.dev/)
    - Another presentation format for slideshows
- [[s.apps.azure.pipelines]]
  - [YAML Schema Reference for pipelines](https://docs.microsoft.com/en-us/azure/devops/pipelines/yaml-schema?tabs=schema%2Cparameter-schema&view=azure-devops)
  - [Pipelines Documentation](https://docs.microsoft.com/en-us/azure/devops/pipelines/?view=azure-devops)
  - Pushing successful Job outputs to [dev](https://docs.microsoft.com/en-us/learn/modules/create-multi-stage-pipeline/4-promote-dev) environment and then [test](https://docs.microsoft.com/en-us/learn/modules/create-multi-stage-pipeline/5-promote-test) environments
    - Leading to [staging](https://docs.microsoft.com/en-us/learn/modules/create-multi-stage-pipeline/6-promote-staging)
- [[s.l.r]] Install packages from [[s.apps.azure.devops]] Repos:

```r
remotes::install_git("<clone url>", git = "external")
```

-  [[s.df.yaml]] [[s.l.python]] The [[s.l.python.libs.pyyaml]] module
      [[s.apps.azure.devops]] naming branches in the repo's using forward slashes in the names groups them under folders:
  - `project/user/branch`

