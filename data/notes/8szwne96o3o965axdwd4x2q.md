

To pass in your author credentials you can use `\author{Bryan Jenks}` and to use it as another argument in another command you can also use `\theauthor`

```latex
% Overwrite existing command '\maktitle'
\renewcommand{\maketitle}{
\begin{center}
{\huge\bfseries
*\theauthor*}
\vspace{.25em}

my email --- https://www.bryanjenks.xyz

\end{center}
} % first new arg from titling package
```
