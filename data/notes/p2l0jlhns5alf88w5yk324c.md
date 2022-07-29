
- [[s.m.markdown]] [[s.m.markdown.extended-functionality.mermaid-diagrams]]
  - Since the vscode plugin for Mermaid syntax highlighting doesn't support the [[s.apps.azure.devops]] wiki syntax of triple colons for the code fence:

```markdown
:::mermaid
  graph TD;
    a-->b
:::
```

  - I actually found an existing issue and added my comment support to it on [The Repo](https://github.com/bpruitt-goddard/vscode-mermaid-syntax-highlight)
- [[s.apps.azure.devops]] The wiki does not like markdown links to section headings even within the document itself. Corrected, its actually just sensitive to some types of headings but section heading links do still actually work

