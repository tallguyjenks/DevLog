---
id: ra6qs7gd8vyyfaws0iw9jcu
title: Pydoc
desc: ''
updated: 1641426617462
created: 1641105063862
stub: false
isDir: false
---


- [Socratica Video](https://www.youtube.com/watch?v=URBSvqib0xw&ab_channel=Socratica)
- using the [[s.l.python.libs.pydoc]] module you can review documentation
- This command ( `python -m pydoc <++>` ) searches for the following:
  - modules ( `math` )
  - classes ( `tuple` )
  - functions ( `pow` )
- [[s.l.python.libs.pydoc]] commands:
  - `pydoc -b`
    - Start an HTTP server with the given hostname (default: localhost).
    - Start an HTTP server on the given port on the local machine. Port number 0 can be used to get an arbitrary unused port.
    - Write out the HTML documentation for a module to a file in the current directory. If `<name>` contains a '' it is treated as a filename; if it names a directory, documentation is written for all the contents.
  - `pydoc -k <keyword>`
    - Search for a keyword in the synopsis lines of all available modules.
    - Start an HTTP server on an arbitrary unused port and open a Web browser to interactively browse documentation. This option can be used in combination with -n and/or - p
  - `pydoc -n <hostname>`
    - Start an HTTP server with the given hostname (default: localhost).
  - `pydoc -p <port>`
    - Start an HTTP server on the given port on the local machine. Port number 0 can be used to get an arbitrary unused port.
  - `pydoc -b`
    - Start an HTTP server on an arbitrary unused port and open a Web browser to interactively browse documentation. This option can be used in combination with -n and/or - p•
  - `pydoc -W <name> ...`
    - Write out the HTML documentation for a module to a file in the current directory. If `<name>` contains a '' it is treated as a filename; if it names a directory, documentation is written for all the contents.
