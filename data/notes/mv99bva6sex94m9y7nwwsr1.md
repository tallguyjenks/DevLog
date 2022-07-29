

## List

```r
# List ----
# The R Objects which can contain elements of different types like 
# Numbers, Strings, Vectors, and another List inside of it
# Syntax: list(data)

#============#
#  EXAMPLES  # ----
#============#

vtr1 = c('hello','world')
vtr2 = c(24.6345,3.6,345.5678)
vtr3 = c(45L,'hi')

ls = list(vtr1,vtr2,vtr3)
ls

# Within each list item/variable returned, it will not let seperate list items/variables
# Dictate the data type of the other items/variable
# It will allow this dictation if inside the variable itself it contains differing
# data types

# Nested Lists ----
list(1,2,list("a","b",list(T,T,F)),"hello",T)
# you can have lists within lists and it displays nested lists effectively in the console

```
