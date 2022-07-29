

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
