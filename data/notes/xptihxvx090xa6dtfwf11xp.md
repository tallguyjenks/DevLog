

```python
with open("employees.txt","r") as employee_file: # Filename, Mode (r:read a:append w:write)
	print(employee_file.readable()) # returns T/F if we can read the file
	print(employee_file.readline()) # reads the first line of the file
	print(employee_file.readline()) # reads the next line (second) in the file
	print(employee_file.readline()[2]) # reads the (third) in the file
# always close open files
employee_file.close() # not necessary if using a context manager `with`


# Python program to illustrate
# Append vs write mode
with open("myfile.txt", "w") as file1:
	L = ["This is Delhi \n", "This is Paris \n", "This is London"]
	file1.writelines(L)
	   
# Append-adds at last
with open("myfile.txt", "a") as file1:  # append mode 
	file1.write("Today \n")
	   
with open("myfile.txt", "r") as file1:
	print("Output of Readlines after appending")
	print(file1.read())
	print()
	   
# Write-Overwrites
with open("myfile.txt", "w") as file1:  # write mode 
	file1.write("Tomorrow \n")
	   
with open("myfile.txt", "r") as file1:
	print("Output of Readlines after writing")
	print(file1.read())
	print()
	
# Output:

#> Output of Readlines after appending
#> This is Delhi
#> This is Paris
#> This is LondonToday
#> 
#> 
#> Output of Readlines after writing
#> Tomorrow
```
