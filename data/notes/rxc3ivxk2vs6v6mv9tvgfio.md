

```python
class softwares:
    names = []
    versions = {}
	
	def __init__(self, names):
		print("running init method")
		if names:
			self.names = names.copy()
			for name in names:
				self.versions[name] = 1
		else:
			raise Exception("Please Enter the names")
	
	def __setitem__(self, name, version):
        print("running set item")
        if name in self.versions:
            self.versions[name] = version
        else:
            raise Exception("Software Name doesn't exist")
    def __getitem__(self,name):
        print("running get item")
        if name in self.versions:
            return self.versions[name]
        else:
            raise Exception("Software Name doesn't exist")
	def __delitem__(self,name):
		print("running del item")
		if name in self.versions:
			del self.versions[name]
			self.names.remove(name)
		else:
			raise Exception("Software Name doesn't exist")
	def __len__(self):
    	return len(self.names)
	def __contains__(self,name):
		if name in self.versions:
			return True
		else:
			return False
#==========================================================================#
p = softwares(['S1','S2','S3'])
p['S1'] = 2 # assigning values to a dictionary is when the __setitem__ dunder is invoked
p['2'] = 2 # assigning values to a dictionary is when the __setitem__ dunder is invoked
 
print(p['S1']) # using the brackets to access a dict value runes the __getitem__ method
print(p['2']) # using the brackets to access a dict value runes the __getitem__ method
# print(p['1']) # throws exception
del p['S1']  # deleting a dictionary key/val pair runs the __delitem__ method
len(p) # runs the class's __len__ method
if 'S2' in p: # this usage of the `in` operator uses the __contains__ function
	print('found!')
	
```
