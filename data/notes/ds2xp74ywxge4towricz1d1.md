
- [[s.l.python]] [Socratica Video](https://www.youtube.com/watch?v=URBSvqib0xw&ab_channel=Socratica)
  - using the [[s.l.python.libs.pydoc]] module you can review documentation
  - This command (`python -m pydoc <++>`) searches for the following:
    - modules (`math`)
    - classes (`tuple`)
    - functions (`pow`)
  - [[s.l.python.libs.pydoc]] commands:
  - `pydoc -k <keyword>`
    - Search for a keyword in the synopsis lines of all available modules.
  - `pydoc -n <hostname>`
    - Start an HTTP server with the given hostname (default: localhost).
  - `pydoc -p <port>`
    - Start an HTTP server on the given port on the local machine. Port number 0 can be used to get an arbitrary unused port.
  - `pydoc -b`
    - Start an HTTP server on an arbitrary unused port and open a Web browser to interactively browse documentation. This option can be used in combination with -n and/or - p•
  - `pydoc -W <name> ...`
    - Write out the HTML documentation for a module to a file in the current directory. If <name> contains a '\\' it is treated as a filename; if it names a directory, documentation is written for all the contents.
    - If <name> contains a '' it is treated as a filename; if it names a directory, documentation is written for all the contents.
- [[s.m.css]]
  - idea of replacing some tags with different appearances:

```css
a.tag[data-ref="star" i]::before {
    content: "⭐";
    visibility: visible;
    border-radius: 2px;
    padding: 2px;
    background: var(--blue);
    box-shadow: 0 0 4px var(--blue);
}

a.tag[data-ref="star" i] {
    visibility: hidden;
    width: 24px;
    white-space: nowrap;
}
```

- from: https://discuss.logseq.com/t/custom-tags-rendering-with-emojis/709

- [[s.q.tsql]]
  - Exporting database objects to files for [[cli.cmd.git]]:
  - _database-->Tasks-->Generate Scripts-->Choose file for each procedure option_
  - Better option for [[cli.cmd.git]] version control is an actual [[cli.cmd.git]] repo via the [[s.q.tsql.tools.redgate]] tool
    - **The Tool:** <https://www.red-gate.com/products/sql-development/sql-source-control/>
    - **About it:** <https://www.youtube.com/watch?v=aR5IHfHvh98>

