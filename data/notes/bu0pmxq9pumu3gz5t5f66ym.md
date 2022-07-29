

## Array

```r
# Array
# The R Objects which can store data in more than 2 dimensions
# Syntax: array(data, dim, dimnames)

#============#
#  EXAMPLES  #
#============#

arr = array(c(0:15),dim = c(4,4,2,2))

#this makes the array = 0-15
#the dimension makes the 0-15 display in a 4x4 grid
#the other dimension makes it a 3d array by making 4 copies of the array in a 
#2x2 grid of arrays
arr

arr2 = array(c(1:9),dim = c(3,3,4,2))
arr2

```
