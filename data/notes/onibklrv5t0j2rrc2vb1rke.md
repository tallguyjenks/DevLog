

## Make Your Own Macros

.de ALL
.B "BIU"
..

First line defines name of macro
next is the contents of the macro
the double dot ends the macro assignment and now its ready to use

Want to keep your custom macros in a seperate file and source them into a document?

use the `.so` \\&lt;file> method to load them
