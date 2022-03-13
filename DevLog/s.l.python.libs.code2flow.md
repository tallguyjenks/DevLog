---
id: vltvhjsdbzabna7vk38sad3
title: Code2flow
desc: ''
updated: 1647148136093
created: 1641451847631
---


- build flow call stack charts of [[s.l.python]] programs
  - use this python module: [code2flow](https://github.com/scottrogowski/code2flow)

## Installation

```bash
pip3 install code2flow
brew install graphviz
```

## Usage

```bash
code2flow my_script.py && open out.png
```

need graphviz installed **OR** use set `--output` to `file_name.dot`

Then use this vscode extension: `tintinweb.graphviz-interactive-preview` to preview it
