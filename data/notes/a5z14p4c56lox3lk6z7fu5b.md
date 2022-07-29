

### Dictionary

```python
# key value pairs, basically an object in javascript
my_dictionary = {"key":"my_key", "value":666}
my_dictionary.keys()
my_dictionary.values()

# to add more key value pairs after initialization to the dictionary use object name and brackets around the key and set equal to the value:
my_dictionary["name"] = "Bryan Jenks"
# with bracket method the key needs quotes around it but in the constructor function you DONT need quotes on the key names:
dict(message="test", language="english")

for key, value in my_dictionary.items():
	print(key, "=", value)
```
