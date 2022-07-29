

## BibLaTeX

Use the package via:

`\usepackage[backend=biber, style=authoryear-icomp]{biblatex}`
`\addbibresource{<file path to .bib file>}`

To print our your bibliography:

`\printbibliography`

`\textcite{<ref>}` will add a reference like _Mould [1]_ but 'Mould' would be the name of the ref you passed in and it has that number but adding `style=authoryear-icomp` to the biblatex package optional arg will change it to _Mould (2003)_ with no brackets and numbers

`\parencite{<ref>}` is what I typically like and use and appears like _(Mould 2003)_

## Documentation

- [OverleafOnBiber](https://www.overleaf.com/learn/latex/Bibliography_management_with_bibtex)

---

- address
- annote
- author
  - booktitle
  - chapter
  - crossref
  - edition
  - editor
  - institution
  - journal
  - key
  - month
  - note
  - number
  - organization
  - pages
- publisher
  - school
  - series
- title
  - type
  - volume
- year
- URL
- ISBN
  - ISSN
  - LCCN
  - abstract
  - keywords
  - price
  - copyright
  - language
  - contents

### Notes

This package is used for references and bibliographies

#### Reference guide

##### Standard entry types

- **article**
  - Article from a magazine or journal
- **booklet**
  - A work that is printed but have no publisher or sponsoring institution
- **conference**
  - An article in a conference proceedings
- **inbook**
  - A part of a book (section, chapter and so on)
- **incollection**
  - A part of a book having its own title
- **inproceedings**
  - An article in a conference proceedings
- **manual**
  - Technical documentation
- **masterthesis**
  - A Master's thesis
- **misc**
  - Something that doesn't fit in any other type
- **phdthesis**
  - A PhD thesis
- **proceedings**
  - The same as conference
- **techreport**
  - Report published by an institution
- **unpublished**
  - Document not formally published, with author and title
