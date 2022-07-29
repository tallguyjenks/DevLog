
Adding a prefix to the router object makes it so you can keep the endpoint path
short and sweet.

passing this:

```python
router = APIRouter (
    prefix="/posts"
)
```

makes it so you can take this code:

```python
@app.get('/posts')
def get_posts():
    ...

@app.get("/posts/latest")
def get_latest_post():
    ...

@app.get("/posts/{id}")
def get_post():
    ...
```

And turn it into this:

```python
@app.get('')
def get_posts():
    ...

@app.get("/latest")
def get_latest_post():
    ...

@app.get("/{id}")
def get_post():
    ...
```
