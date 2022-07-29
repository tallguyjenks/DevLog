

|     Groff cmd      |     LaTeX cmd      |   markdown   |                         What it is                          |
| :----------------: | :----------------: | :----------: | :---------------------------------------------------------: |
|       `.TL`        |     `\title{}`     |              |                            Title                            |
|       `.AU`        |    `\author{}`     |              |                           Author                            |
|       `.AB`        | `\begin{abstract}` |              |                       Start Abstract                        |
|       `.AE`        |  `\end{abstract}`  |              |                        End Abstract                         |
|       `.NH`        |    `\section{}`    |      #       |                     A Numbered section                      |
|       `.SH`        |    `\section{}`    |      #       |                   A Non-Numbered heading                    |
|       `.LP`        |                    |              |                      A Left Paragraph                       |
|       `.PP`        |   `\paragraph{}`   |              |                    An Indented Paragraph                    |
|       `.QP`        |                    |              |        A quoted Paragraph, `.PP` but multiple lines         |
|     `.B`"TEXT"     |    `\textbf{}`     |    _text_    |                            Bold                             |
|     `.I`"TEXT"     |    `\textit{}`     |    _text_    |                           Italics                           |
|       `.QS`        |                    |              |                   Start Quoted text block                   |
|       `.QE`        |                    |              |                    End Quoted text block                    |
|       `.IP`        |                    |              | Indent paragraph can add symbol before and make bullet list |
|       `\(bu`       |                    |      -       |    Bullet arg after `.IP` to make it a bullet point list    |
|       `.RS`        |                    |              |             Start indent List `.IP` list items              |
|       `.RE`        |                    |              |              End indent List `.IP` list items               |
| `\f[I]`TEXT`\f[]`  |    `\textit{}`     |    _text_    |                 Inline italic font styling                  |
| `\f[B]`TEXT`\f[]`  |    `\textbf{}`     |    _text_    |                  Inline bold font styling                   |
| `\f[CW]`TEXT`\f[]` |    `\texttt{}`     |    `text`    |             Inline constant Width font styling              |
| `\f[BI]`TEXT`\f[]` |                    |  **_text_**  |              Inline bold italics font styling               |
|       `.\"`        |        `%`         | <!-- text--> |                          A comment                          |
|       `.B1`        |                    |              |                     Start a box of text                     |
|       `.B2`        |                    |              |                     Stop a box of text                      |
|       `.BX.`       |                    |              |      Make box form fitting to text and no wasted space      |
|    `.UL` "TEXT"    |                    | <u>text</u>  |                       Underlined text                       |
|   `\*{super\*}`    |                    |    ^text^    |                        Super script                         |
|       `.bp`        |    `\pagebreak`    |              |                       break the page                        |
|       `.TS`        | `\begin{tabular}`  |              |                        Start a table                        |
|       `.TE`        |  `\end{tabular}`   |              |                         end a table                         |
|   `.nr` name val   |                    |              |          assignment `val` to named register `name`          |
|    `\\n[name]`     |                    |              |               print value of register `name`                |
|     `.ds` name     |                    |              |    Define string, all after 'name' is part of string val    |
|     `\*[name]`     |                    |              |                     Print string value                      |
|                    |                    |              |                                                             |
