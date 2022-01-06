---
id: bCY9XAz5Hj8q8jlkcX19A
title: Dictionary Access with Get
desc: ''
updated: 1641423130656
created: 1641423130656
---

## Stop Using Square Brackets To Get Dictionary Items — Use .get()

### Before

```python
nik = {
'age':32,
'gender':'male',
'employed':True,
}

print(nik['location'])

# Returns:
# KeyError: 'location'
```

### After

```python
nik = {
'age':32,
'gender':'male',
'employed':True,
}

print(nik.get('location'))

# Returns:
# None
```
