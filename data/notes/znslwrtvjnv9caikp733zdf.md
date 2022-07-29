

### API Root

```python
# This is a path operation / or also called a route
@app.get('/') # this actually converts this function into an API end point that the user can access
#    │   └──── The path operation, this is what happens when the users goes to the root, it path was `/login` then the user would only get here if they went to our site and `/login`
#   └───────── The GET HTTP method is used to retrieve data from a server
async def root():
    return {"message": "Hello from my API"} # fastapi automatically converts to JSON
```

#### Root Without Comments

```python
@app.get('/')
async def root():
    return {"message": "Hello from my API"}
```
