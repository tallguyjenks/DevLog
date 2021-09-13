-
			  ```python
			  with open("employees.txt","r") as employee_file: # Filename, Mode (r:read a:append w:write)
			    print(employee_file.readable()) # returns T/F if we can read the file
			    print(employee_file.readline()) # reads the first line of the file
			    print(employee_file.readline()) # reads the next line (second) in the file
			    print(employee_file.readline()[2]) # reads the (third) in the file
			  			  			  			  			  			  			  				  
			  			  			  			  			  			  			  				  
			  # always close open files
			  employee_file.close() # not necessary if using a context manager `with`
			  ```