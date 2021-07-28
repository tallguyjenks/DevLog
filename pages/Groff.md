---
tags:
aliases:
cssclass:
---

#### [[Groff]]

---

| Groff cmd          | LaTeX cmd          | markdown     | What it is                                                  |
| :------:          | :------:          | :-----:     | :------:                                                  |
| `.TL`              | `\title{}`         |              | Title                                                       |
| `.AU`              | `\author{}`        |              | Author                                                      |
| `.AB`              | `\begin{abstract}` |              | Start Abstract                                              |
| `.AE`              | `\end{abstract}`   |              | End Abstract                                                |
| `.NH`              | `\section{}`       | #            | A Numbered section                                          |
| `.SH`              | `\section{}`       | #            | A Non-Numbered heading                                      |
| `.LP`              |                    |              | A Left Paragraph                                            |
| `.PP`              | `\paragraph{}`     |              | An Indented Paragraph                                       |
| `.QP`              |                    |              | A quoted Paragraph, `.PP` but multiple lines                |
| `.B`"TEXT"         | `\textbf{}`        | *text*       | Bold                                                        |
| `.I`"TEXT"         | `\textit{}`        | _text_       | Italics                                                     |
| `.QS`              |                    |              | Start Quoted text block                                     |
| `.QE`              |                    |              | End Quoted text block                                       |
| `.IP`              |                    |              | Indent paragraph can add symbol before and make bullet list |
| `\(bu`             |                    | -            | Bullet arg after `.IP` to make it a bullet point list       |
| `.RS`              |                    |              | Start indent List `.IP` list items                          |
| `.RE`              |                    |              | End indent List `.IP` list items                            |
| `\f[I]`TEXT`\f[]`  | `\textit{}`        | _text_       | Inline italic font styling                                  |
| `\f[B]`TEXT`\f[]`  | `\textbf{}`        | *text*       | Inline bold font styling                                    |
| `\f[CW]`TEXT`\f[]` | `\texttt{}`        | `text`       | Inline constant Width font styling                          |
| `\f[BI]`TEXT`\f[]` |                    | __*text*__   | Inline bold italics font styling                            |
| `.\"`              | `%`                | <!-- text--> | A comment                                                   |
| `.B1`              |                    |              | Start a box of text                                         |
| `.B2`              |                    |              | Stop a box of text                                          |
| `.BX.`             |                    |              | Make box form fitting to text and no wasted space           |
| `.UL` "TEXT"       |                    | <u>text</u>  | Underlined text                                             |
| `\*{super\*}`      |                    | ^text^       | Super script                                                |
| `.bp`              | `\pagebreak`       |              | break the page                                              |
| `.TS`              | `\begin{tabular}`  |              | Start a table                                               |
| `.TE`              | `\end{tabular}`    |              | end a table                                                 |
| `.nr` name val     |                    |              | assignment `val` to named register `name`                   |
| `\\n[name]`        |                    |              | print value of register `name`                              |
| `.ds` name         |                    |              | Define string, all after 'name' is part of string val       |
| `\*[name]`         |                    |              | Print string value                                          |
|                    |                    |              |                                                             |

# tables

.TS
options ;
format .
table
.TE
\---
.TS
allbox ;
c c c .
a|a|a
.TE
\---
.\" Make it so all borders show and tab character represented by pipe.
.\" c = center s = skip, l = left align, n = numeral based
.\" Each line of formatting corresponds to the line of data 1st format line first line of data

.TS
allbox tab(|);
c s s s
c s c s
n c c c.
Title
sub |sub
a |a |a| a
a |a |a| a
AFGDGHDFH |a |a| a
.TE
\---
.TS
tab(|);
c s s s
c s |c s
n c |c c.
Title
_
sub |sub
_
a |a |a| a
a |a |a| a
AFGDGHDFH |a |a| a
.TE


| Groff cmd          | LaTeX cmd                      | markdown | What it is    |
| :------:          | :------:                      | :-----: | :------:    |
| `.PSPIC` "file"    | `\includegraphics{`filepath`}` | ![ ] ( ) | insert images |
|                    |                                |          |               |



`.PSPIC` -[CLR] options for image alignment/ center default
%% I option for indent image followed by num and unit
`.PSPIC` -I 1i "img" 4i 2i
%% Indents = indent, Width Height

%% grab a screenshot image
`:!screenshot -ws <filename>`
%% convert captured image to postscript for import
`:!convert <inputfile> <outputfile.eps>`
%% Compile to see images
%% also script a key to open the preview in external viewer


# Make Your Own Macros

.de ALL
.B "BIU"
..

First line defines name of macro
next is the contents of the macro
the double dot ends the macro assignment and now its ready to use

Want to keep your custom macros in a seperate file and source them into a document?

use the `.so` \<file\> method to load them


# Variables

%% Assigns 3 to variable var
.nr var 3
%% prints var
\n[var]
%% increment var by 4
.nr var +4
\n[var]

---
Tags: 

Reference:

Related:

