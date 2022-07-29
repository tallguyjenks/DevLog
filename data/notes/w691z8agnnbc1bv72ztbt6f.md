

```r
# Functions ----
# Descriptive Statistics Functions ----

myValues <- c(1:100)
myValues

mean(myValues)
median(myValues)
mode(myValues)
min(myValues)
max(myValues)
sum(myValues)
sd(myValues) #standard deviation
class(myValues)
length(myValues)
log(myValues)
log10(myValues)


mySqrt <- sqrt(myValues)
mySqrt

?rnorm # Adding a question mark before the name of a function opens a help pane with all the details
# on that function, this is a great way to learn about what the functions require as arguments
?rgb

hist(rnorm(100, mean = 5))

# Data frame Functioons ----

# setting up the data frame vectors
id <- 1:200
group <- c(rep("Vehicle",100),
	   rep("Drug",100))
response <- c(rnorm(100,mean = 25, sd = 5),
		  rnorm(100,mean = 23, sd=5))

#compiling the data frame
myData <- data.frame(Patient = id,
				 Treatment = group,
				 Response = response)

myData
head(myData,10)
tail(myData,10)
dim(myData)
str(myData)
summary(myData)


# Change Value of data type present can work for entire columns ----
as.numeric(c("1","2","3"))
as.character(1:10)


# Remove Objects ----
# Objects names cannot contain  spaces in varialbe/object names 
# But underscores and periods allowed but best to just stick with camel case

my_Object <- 3
my.Object <- 3
myObject <-3

# all of these are valid
# to remove an object use the RM command

rm(my_Object)
rm(my.Object)
```
