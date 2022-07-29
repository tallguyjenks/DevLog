

## Syntax

Some Markdown processors support custom heading id's determined by this syntax:

```
### My Great Heading {#custom-id}
```

The HTML looks like this:

```
<h3 id="custom-id">My Great Heading</h3>
```

## rmarkdown

In Rmarkdown next to the HTML headings you can input additional metadata within braces like this flexdashboard code:

```md
## Page 1 {data-navmenu="Menu A" .hidden}
```
