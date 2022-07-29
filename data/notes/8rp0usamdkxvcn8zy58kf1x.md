

## Syntax

In Markdown inline code can be formatted with backticks \`code\`

`code`

and multi line code can be done with fenced code areas

````
```
Multi
line
code
```
````

when you want to display code inline is one back tick

`` `incline` ``

when you want to show the backticks in formatted code its 2 backticks

``` `` some `code` in line with backticks`` ```

when you want to display a code fenced block including back ticks you sandwich the 3 backtick code fence inside of a 4 backtick fence:

`````
````
```
code fence
```
````
`````

and to keep showing more levels of backtick sandwiches just keep increasing the amount of backticks, the code for the above image is:

![alt](assets/images/Pasted_image_20201207031806.png)

## RMarkdown

in rmarkdown you can have r code executed inline with the following syntax:

```
`r mean(5,10)`
```

In Rmarkdown the fenced code chunks have a slightly different syntax to allow for control options and meta-processing options:

````
```r{ control_option}
x <- 7
```
````
