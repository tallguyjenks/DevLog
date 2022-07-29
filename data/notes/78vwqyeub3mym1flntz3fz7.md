

## Vectors

```r
#vectors ----
#5 types
# Logical
# Integer
# Numeric 'value greater than 7 digits will always be converted to the exponential format
# Complex
# Character

#============#
#  EXAMPLES  #----
#============#

#Logical
vtr1 = c(TRUE,FALSE)

#Numeric
vtr2 = c(15,85.674954,999999)

#Integer requires "L" after number to treat as integer
vtr3 = c(35L,58L,146L)

#Integer with decemals converted with warning to numeric
vtr4 = c(85.64L)

#Wrong data types passed to vector
vtr5 = c(TRUE,35L,3.14) #TRUE will be converted to Boolean 1 if put into a Numeric/Integer Vector

#now incude a character string
vtr6 = c(TRUE,35L,3.14,"hello")

#===========#
#  Results  #----
#===========#

class(vtr1)
vtr1
class(vtr2)
vtr2
class(vtr3)
vtr3
class(vtr4)
vtr4
class(vtr5)
vtr5
class(vtr6)
vtr6

# Vector Math ----

numbers <- c(1:10)
numbers * 2

# Subsetting Vectors ----

days <- c("mon", "tue", "wed", "thurs", "fri")
days
# to return a specific value of a vector in square brackets after its object holding the vector
# use square brackets and the index of the value to pull out a subset of a vector
days[1]
# square brackets are ALWAYS for subsetting the parens "()" are for functions
days[c(1,3,5)] #vector within the sub setting brackets to pull out specific values
days[2:5] #if you wanted everything except monday
days[-5] #basically saying "give me everything except what's in index 5" or in this case "Friday

```
