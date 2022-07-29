

## The \_\_main\_\_ Function

```python
import time

def useful_function():
	for i in range(5):
		print("I sweat I'm useful: {}".format(i))
		time.sleep(1.0)

# This function call if un commented would make it so if the script was run
# on the CLI then it would execute the function code. However, if we want to 
# Re-use the code as a module import and not have it run immediately on import
# Then you need the following logical construct
# useful_function()

# This code checks if the entry point to the current session is this file.
# i.e. did we run this file like a script? or are we importing from another 
# location that is actually "__main__" and we're a sub process declaring
# variables, functions, and classes? Anything under this construct is ran and 
# defined only if the script is executed as a stand alone script and not imported
if __name__ == "__main__":
	useful_function()
```
