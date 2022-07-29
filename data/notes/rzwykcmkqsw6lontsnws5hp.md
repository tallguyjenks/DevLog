

## Order matters

If your API function has a path parameter then your other more specific paths need to come before it so that it doesnt think part of the path is the expected input parameter

```python
@app.get("/posts/latest")
def get_latest_post():
    post = my_posts[len(my_posts) - 1]
    return {"detail": post}

@app.get("/posts/{id}")
def get_post(id: int):
    post = find_post(id)
    return {"post_detail": post}
```
