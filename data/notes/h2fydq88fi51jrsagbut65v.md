

- Internal Links
  - `[[Internal Link]]`: links to a file named `Internal Link`
    - `[[Internal Link|Hello]]`: Changes display text of the link to `Hello`
  - `[[Internal Link#Welcome]]`: Links to an H1 heading in `Internal Link` that says `Welcome`
    - `[[Internal Link#Welcome|Hello]]`: Changes display text of the link to `Hello`
  - `[[Internal Link#^5e6366]]`: Links to a block in the `Internal Link` document
    - `[[Internal Link#^5e6366|Hello]]`: Changes display text of the link to `Hello`
- Transcluded (embedded Links)
  - `![[Internal Link]]`: Transcludes a file named `Internal Link`
  - `![[Internal Link#Welcome]]`: Transcludes content under the H1 heading in `Internal Link` that says `Welcome`
  - `![[Internal Link#^5e6366]]`: Transcludes a block in the `Internal Link` document
- Image Links
  - `![[Internal Link.png)`: Inserts an image named `Internal Link`
    - `[![[Internal Link.png)](https://www.bryanjenks.dev)`: Make an image have a hyperlink
