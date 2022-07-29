

### Get

```python
@app.get('/posts') # in this instance this data gets returned to the user at 127.0.0.1:8000/posts
# Due to granularity for the paths in the decorators if there are duplicates then the first one that matches is chosen
def get_posts():
    return {"data": "this is your posts"}
```

#### Get Without Comments

```python
@app.get('/posts')
def get_posts():
    return {"data": "this is your posts"}
```
