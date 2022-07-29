

## Data Frame

```r
# PART 1 ----

# Data Frames
# A Table or a 2-dimensional array-like structure in which each column contains 
# values of one variable and each row contains one set of values from each column
# Syntax: data.frame(data)

#============#
#  EXAMPLES  #
#============#

RowCount = c(1:5)
PeopleNames = c("Bryan","Jude","kelly","janelle","Rosa")
Values = c(15,25,65,145,74)

df <- data.frame(RowCount,PeopleNames,Values)
df
# This alone will display the valeus of the data frame each vector in the frame
# represents a vertical column of values that each contibue a value to each row

data.frame(airquality) 
# Built in sample data table, can also import Excel files


# PART 2 ----

myDataFrame <- read.csv("20190208 RC Registry.csv")
myDataFrame <- myDataFrame[myDataFrame$Medical..Screening.Due.Date <date, c("CDCR", "Medical..Screening.Due.Date")]
myDataFrame


# PART 3 ----

# setting up the data frame vectors
id <- 1:200
group <- c(rep("Vehicle",100),
	   rep("Drug",100))
response <- c(rnorm(100,mean = 25, sd = 5),
		  rnorm(100,mean = 23, sd=5))
age <- round(rnorm(200,40,20))

#compiling the data frame
myData <- data.frame(Patient = id,
				 Patient.Age = age,
				 Treatment = group,
				 Response = response)

myData
head(myData,10)
tail(myData,10)
dim(myData)
str(myData)
summary(myData)

# subsetting Data.frames ----

myData[1,2]
myData[2,3]
myData[1:20,2:3] # first 20 rows with columns 2 & 3 present
myData[1:20,] # returns 20 rows and all columns if left blank
myData[,1] # returns everythingh in the first column only
myData[,"Response"] # returns just the columns values for the column named "Response"
myData$Response #the Dollar sign $ after the name of the data frame will return the entire column without quotes or brackets

myData[myData$Response>26,] # give me the rows and all columns for every row that meets the criteria
# of Response > 26

#perform a calculation and then add values to a new column of the data frame
myData$Positive <- myData$Response<26
write.csv(myData[myData$Response>26,],file = "testData.csv", row.names = F) # write a CSV file to the current working directory

# multiple filter criteria and then assigned
# to a new object for ease of exporting to CSV
CSVMyData <- myData[myData$Treatment == "Vehicle"
				& myData$Response>26 &
					myData$Patient.Age > 0,] 


write.csv(CSVMyData,file = "testData.csv", row.names = F)

head(CSVMyData)

```
