

## Matrix

```r
# Matrix
# R Objects in which the elements are arranged in a 2 dimensional rectangular layout
# Syntax: matrix(data, nrow, ncol, byrow, dimnames)
# Data: the input vector which becomes the data elements of the matrix
# NRow: number of rows to be created
# NCol: number of columns to be created
# ByRow: a logical clue. If TRUE then the input vector elements are arranged by row
# DimName: The names assigned to the rows and columns

#============#
#  EXAMPLES  #
#============#

mtr = matrix(c(1:25),5,5)
mtr
# Warning message:
# In matrix(c(5:30), 5, 5) :
# data length [26] is not a sub-multiple or multiple of the number of rows [5]
# If your total number of data points spills out of the matrix, error returns

```
