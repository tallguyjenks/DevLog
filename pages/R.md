---
collapsed:: false
title: R
tags: language
---

- **Language**
  collapsed:: false
	- ^^Setup^^
	- ^^Resources^^
		- [Ten random useful things in R that you might not know about](https://towardsdatascience.com/ten-random-useful-things-in-r-that-you-might-not-know-about-54b2044a3868)
		- [HexSticker Maker](https://connect.thinkr.fr/hexmake/)
		- [Control HTML Code Folding](https://stackoverflow.com/questions/37755037/how-to-add-code-folding-to-output-chunks-in-rmarkdown-html-documents)
		- [R Seek](https://rseek.org/)
		- [R Graph Gallery](https://www.r-graph-gallery.com/)
		- [knitr Options](https://yihui.org/knitr/options/)
		- [Pimp my Rmd](https://holtzy.github.io/Pimp-my-rmd/)
	- ^^Package Development^^
		- [Pkg Dev From Scratch](https://hilaryparker.com/2014/04/29/writing-an-r-package-from-scratch/)
		- [R Pkgs Book](https://r-pkgs.org/index.html)
		-
	- ^^Tools^^
	- ^^Libraries^^
		- **Visualization:** [[ggplot2]], [[shiny]]
		- **Documentation:**
		- **Development:**
		- **Stylistic:**
		- **Data Wrangling:**
			- **Acquisition:** [[pins]]
			- **Cleaning:** [[dplyr]]
			  id:: 60f29a74-8b74-4232-8ce6-5ac8119c9b26
	- ^^Projects^^
	- ^^Syntax^^
		- **Base R**
		  collapsed:: true
			- # How to add indexed areas to your R script:
				-
				  ```r
				  # Steps:
				    # 1.) Add the hashtag in line to start the comment
				    # 2.) Type what you'd like then space
				    # 3.) then add 4 dashes "----"
				  # This will inxes your code area and make it collapsable as well
				  # the indexed option appears at the bottom of this window 
				  
				  # PART A ----
				  print("Hello World")
				  # PART B ----
				  ```
				-
				  ```r
				  # empty value ----
				  
				  NA #NA is a logical constant of length 1 which contains a missing value indicator
				  
				  NULL #NULL represents the null object in R: 
				  # it is a reserved word. NULL is often returned by expressions and 
				  # functions whose value is undefined.
				  
				  ?NA
				  ```
			- # Conditional Statements
			-
			  ```r
			    # IF
			        # Syntax:
			            # if(expression)
			            #   {
			            #        //statements
			            #   }
			    # ELSE IF
			        # Syntax:
			            # if(expression 1)
			            #   {
			            #        //statements
			            #   }
			            # Else If(expression 2)
			            #   {
			            #        //statements
			            #   }
			  
			  
			  vtr1 <- c(5)
			  
			  if(vtr1==5)
			  {
			    print("hello world")
			  }
			  ```
			- # Data Operators
			  
			  ```r
			    # Arithmatic
			        # Addition (+)
			        # Subtraction (-)
			        # Multiplication (*)
			        # Division (/)
			        # Modulus (%%)
			        # Exponent (^)
			        # Floor Division (%/%)
			    # Relational
			        # Equal To (==) #asking "is this equal to that" returns Bool
			        # Not Equal To (!=)
			        # Greater Than (>)
			        # Less Than (<)
			        # Greater Than Equal To (>=)
			        # Less Than Equal To (<=)
			    # Assignment
			        # Left
			        # Equals (=)
			        # Assign (<-)
			        # Right
			        # Equals (=)
			        # Assign (->)
			    # Logical
			        # AND (&) in 2 concurrent vectors, compare each aligned item ask AND
			        # AND (&&) compre whole vector to whole vector and all AND's need to be
			        # TRUE or else False
			        # NOT (!)
			        # OR (|) in 2 concurrent vectors, compare each aligned item ask OR
			        # OR (||) compareshole vector to whole vector and either side needs
			        # to be TRUE or else False 
			  ```
			- # Data Types
				- ## Vectors
				  collapsed:: true
					-
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
				- ## Matrix
				  collapsed:: true
					-
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
				- ## Array
				  collapsed:: true
					-
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
				- ## List
				  collapsed:: true
					-
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
			- ## Data Frame
			  collapsed:: true
				-
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
			- ## Data Classes
			  collapsed:: true
				-
				  ```r
				  # Data Classes ----
				  
				  12.6    #Numeric
				  3       #Numeric
				  100     #Numeric
				  
				  "male"  #Character
				  
				  TRUE    #Logical
				  FALSE   #Logical
				  T       #Logical
				  F       #Logical
				  
				  # Data Structures ----
				  
				  # Vector
				  # List
				  # Matrix
				  # Data Frame
				  ```
			- ## Functions
			  collapsed:: true
				-
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
	- ^^Data Types & Structs^^
	- ^^Flow Control^^
	- ^^Functions^^
	- ^^Object Oriented Programming^^
	- ^^File Handling^^
	- ^^Tips, Tricks, & Hacks^^