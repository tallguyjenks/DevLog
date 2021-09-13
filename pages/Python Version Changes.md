- **3.10**
	- _Structural Pattern Matching_
		- From:
			-
			  ```python
			  name = input() 
			  match name: 
			      case "Misha": 
			     return "Hello Misha" 
			      case "John": 
			     return "Hello John" 
			      case _: 
			     return "Go away"
			  ```
			- - To:
			-
			  ```python
			  match name: 
			      case "Misha" | "John": 
			     return f"Hello {name}" 
			      case "Michelle": 
			     return "Long time no see, Michelle" 
			      case _: 
			     return "Go away"
			  ```
		- Add Additional Conditions on matches with `if`
			-
			  ```python
			  
			  def get_car_price(make, is_turbocharged): 
			      match make: 
			     case "Subaru" if is_turbocharged: 
			         return 10000 
			     case "Toyota" if not is_turbocharged: 
			         return 7500 
			     case _: 
			         return 2300
			  ```
			- - [Video on Pattern Matching](https://youtu.be/-79HGfWmH_w)
				- - _Union Operator for Type Hints_
					-
					  ```python
					  def add(x: int | float, y: int | float):
					    return x + y
					  ```
	- _Parenthesized Context Managers_
		-
		  ```python
		  with (open('file1.txt', 'r') as fin, 
		   open('file2.txt', 'w') as fout):
		  fout.write(fin.read()) 
		  # In essence: cat file1.txt > file2.txt 
		  # if file2 were in append mode 'a' then it would be like: 
		  # cat file1.txt >> file2.txt
		  ```
		-