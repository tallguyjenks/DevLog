

### Post

```python
from fastapi.params import Body
from pydantic import BaseModel

 @app.post('/posts') # V1
 def create_posts(payLoad: dict = Body(...)): # Take in the body (data) of the POST request and do stuff with it
     print(payLoad)
     return {"new_post": f"{payLoad['title'] =} {payLoad['content'] =}"}

#===========================================================================#

@app.post('/posts') # V2
def create_posts(new_post: Post): # Take in the body (data) of the POST request and do stuff with it
    print(new_post)
    return {"new_post": f"{new_post.title =} {new_post.content =}"}
```
