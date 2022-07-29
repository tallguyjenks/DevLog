

## Resources

- <https://www.youtube.com/4f3AENLrdYo>

Generate tags so that you can jump to function definitions
in a file or in a group of files. tags will also find their
definitions in other files in the director(ies) it was generated in

To generate tags: `ctags -R .`

this generates a `tags` file and now in your documents you can use
the following keybindings:

`ctrl-]` jump to definition
`ctrl-o` go back to prior position
`ctrl-i` Jump forward

`:h tag-stack` for more info on tags
