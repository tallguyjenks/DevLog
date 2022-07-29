

## File Separator

> "The file separator FS is an interesting control code, as it gives us insight in the way that computer technology was organized in the sixties. We are now used to random access media like RAM and magnetic disks, but when the ASCII standard was defined, most data was serial. I am not only talking about serial communications, but also about serial storage like punch cards, paper tape and magnetic tapes. In such a situation it is clearly efficient to have a single control code to signal the separation of two files. The FS was defined for this purpose."
> <br>
> Nowadays we still need a way to delimit files within a serialized stream, for example when uploading photos on a website. But how do we get around the fact that each file, especially a non-text image file, could itself contain the FS character? The MIME spec calls for a custom-defined boundary, and suggests using an improbable string of gibberish:

```
Content-Type: multipart/mixed;
     boundary=gc0p4Jq0M2Yt08jU534c0p
```
