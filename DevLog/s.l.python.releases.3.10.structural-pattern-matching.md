---
id: 4ww4db346e8z1338sqz620j
title: Structural Pattern Matching
desc: ''
updated: 1641423345597
created: 1641423345597
---


## Structural Pattern Matching

#### From

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

#### To

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

- [Video on Pattern Matching](https://youtu.be/-79HGfWmH_w)
