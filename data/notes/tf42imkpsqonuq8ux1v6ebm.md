

|    Groff cmd    |           LaTeX cmd            | markdown  |  What it is   |
| :-------------: | :----------------------------: | :-------: | :-----------: |
| `.PSPIC` "file" | `\includegraphics{`filepath`}` | ![ ] \( ) | insert images |
|                 |                                |           |               |

`.PSPIC` - [CLR] options for image alignment/ center default

I option for indent image followed by num and unit

`.PSPIC` - I 1i "img" 4i 2i

Indents = indent, Width Height

grab a screenshot image

`:!screenshot -ws <filename>`

convert captured image to postscript for import

`:!convert <inputfile> <outputfile.eps>`

Compile to see images

also script a key to open the preview in external viewer
