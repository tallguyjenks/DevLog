

## Title

`\title{My {\LaTeX} R\'esum\'e}`

your title is defined in the title command but this is outsize of your document body, inside the document body you actually call:

`\maketitle`

to render your title onto the document

you can customize the title with the [[LaTeX Titling|s.m.latex.pkg.titling]] package and the renewcommand command like so:

```latex
\renewcommand{\maketitle}{
\begin{center}
{\huge\bfseries
\theauthor}
\vspace{.25em}

my email --- https://www.bryanjenks.xyz

\end{center}
} % first new arg from titling package
```

## Documentation

- [titlesec](https://mirrors.concertpass.com/tex-archive/macros/latex/contrib/titlesec/titlesec.pdf)
