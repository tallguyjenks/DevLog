
   
-  [[s.l.python]] [[s.l.python.libs.watermark]] [[s.l.python.tools.jupyter]] [Calm Code Watermark][1]
  -  move browser technical links to logseq
-  [[s.apps.azure.devops]] [Implementing DevSecOps in Azure][2]
-  [[s.apps.azure.pipelines]] [[s.apps.azure.devops]] [[R|r]] [Azure DevOps Pipelines for deploying content to RStudio Connect][3]
  -  [[s.l.python]] [Absolute vs Relative Imports in Python][4]
  - importing a package, essentially is importing the `__init__.py` module a module is any .py file
    - so having the `__init__.py` importing the other modules is how you load the whole thing in one go
  - Absolute imports are recommended in PEP8: 
  - but when you have a crazy directory structure
    - `from package1.subpackage2.subpackage3.subpackage4.module5 import function6`
    - sometimes relative may be preferred
-  add pre-commit hooks for markdown somehow, settings auto fix via linter and pre-commit hooks?
  -  [[s.l.python]] [10 common security gotchas in Python and how to avoid them][5]

[1]: https://calmcode.io/shorts/watermark.py.html
[2]: https://www.nearform.com/blog/getting-devsecops-right-in-azure/
[3]: https://medium.com/rstudio-connect-digest/azure-devops-pipelines-for-deploying-content-to-rstudio-connect-e992f49103b6
[4]: https://realpython.com/absolute-vs-relative-python-imports/
[5]: https://hackernoon.com/10-common-security-gotchas-in-python-and-how-to-avoid-them-e19fbe265e03
