

## tables

```troff
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
```
