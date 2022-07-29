

## C1 Next Line

> "LF, having two alternative functions, has been a major source of confusion. While LF was initially defined as a "move down" operator, standards began to allow LF as a newline too. As a result, operating systems differ in their definition of a newline. A newline is LF on Unix. Operating systems using CR LF include CP/M, DOS, OS/2 and Windows. Naturally, this caused an incompatibility. To solve the problem, control characters IND and NEL were added to the C1 area. This did not solve the issue, resulting in IND being removed later.
> <br>
> Note: NEL maps to the control character NL (New Line) in the EBCDIC character set used on IBM mainframes."
> <br>
> EBCDIC is an encoding descended from punched cards and the six bit decimal code used with most IBMs of the late 1950s and early 1960s. Wikipedia has a great picture of such a punch card.
> <br>
> Finally, in the early 1990s when it was becoming increasingly obvious that the Internet, and soon the burgeoning World Wide Web in particular, would require a character set that supported all multilingual text, Unicode was born. By the time Unicode hit version 1.1 in 1993, it included the majority of common European- and Asian-based characters as well as—surprise, surprise—a few new control characters of course:
> <br>
> "A paragraph separator--independent of how it is encoded--is used to indicate a separation between paragraphs. A line separator indicates where a line break alone should occur, typically within a paragraph. For comparison, line separators basically correspond to HTML `<BR>`, and paragraph separators to older usage of HTML `<P>` (modern HTML delimits paragraphs by enclosing them in `<P>`...`</P>`).
> <br>
> The Unicode Standard defines two unambiguous separator characters: U+2029 (PS) and U+2028 (LS). In Unicode text, the PS and LS characters should be used wherever the desired function is unambiguous."
> <br>
> Yes, this surely made everything better.
> <br>
> Given the reality of reading CSVs, at best a loose convention with more interpretations and incarnations than even the newline, the most sanity-preserving path is usually to stick to the basic newlines (LF, CR+LF, CR) and call it a day, if you can get away with it.
> <br>
> But if one day you encounter a VT masquerading as a space in the text editor, or rescue some long-siloed database that was instructed by its departed master to delimit records with RS, perhaps you'll recall the enigmatic history of these dust-gathering control characters.
