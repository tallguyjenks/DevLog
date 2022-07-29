

```python
class point:
    x = None
    y = None
    
    def __init__(self, x , y):
        self.x = x
        self.y = y
    
    def __str__(self):
        s = f'({self.x},{self.y})'
        return s

	def __add__(self, p2):
		x = self.x + p2.x
		y = self.y + p2.y
		return point(x,y)
	
	def __iadd__(self, p2):
		self.x += p2.x
		self.y += p2.y
		return self

p1 = point(5,4)
p2 = point(2,3)

p3 = p1 + p2 # this runs the __add__ method
# >>> p3 = (7,7)

p1 += p2
# >>> p1 = (7,7)
```
