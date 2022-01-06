---
id: eVUCbj1NLCMlrxoH9PA5G
title: Example
desc: ''
updated: 1641408543407
created: 1641408543407
---

### Examples

```latex
\titleformat{\section}[frame]
{\huge}
{}
{.25em} % The only required argument
{\filcenter\bfseries\lowercase}% Horizontal line [\titlerule] % Optional param

% SubSection Formatting
\titleformat{\subsection}
{\bfseries\Large}
{\hspace{-.25in}$\bullet$}
{.3em}
{}

% SubSubSection Formatting
\titleformat{\subsubsection}[runin] % Optional param
{\bfseries}
{}
{0em}
{}[---]

\titleformat{\section}[frame]
{\normalfont}
{\filright\footnotesize\enspace SECTION \thesection\enspace}
{8pt}
{\Large\bfseries\filcenter}
```
