

## Input Groups

```python
#!/usr/bin/env python

from pywebio.input import *
from pywebio.output import *

data = input_group(
  "User data",
  [
	  input("What is your Name?", name="name", type=TEXT),
	  input("Input your age", name="age", type=NUMBER),
	  radio(
		  "Which Continent?",
		  name="continent",
		  options=[
			  "Africa",
			  "Asia",
			  "Australia",
			  "Europe",
			  "North America",
			  "South America",
		  ],
	  ),
	  checkbox(
		  "User Term", name="agreement", options=["I agree to terms and conditions"]
	  ),
  ],
)

# Output functions

put_text("The output in a table:")

put_table(
  [
	  ["Name", data["name"]],
	  ["Age", data["age"]],
	  ["Continent", data["continent"]],
	  ["Agreement", data["agreement"]],
  ]
)
```
