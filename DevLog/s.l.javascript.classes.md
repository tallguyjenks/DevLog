---
id: si38g68ni5l81zp3usxi4e6
title: Classes
desc: ''
updated: 1641406539404
created: 1641105063909
stub: false
isDir: false
---


JavaScript Classes are templates for JavaScript Objects.

Use the keyword `class` to create a class.

Always add a method named `constructor()`:

```js
class Car 
{  
	constructor(name, year) 
	{  
		this.name \= name;  
		this.year \= year;  
	}  
}
```

A JavaScript class is **not** an object.

It is a **template** for JavaScript objects.

```js
let myCar1 = new Car("Ford", 2014);  
let myCar2 = new Car("Audi", 2019);
```
