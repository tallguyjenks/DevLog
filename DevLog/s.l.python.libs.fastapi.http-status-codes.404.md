---
id: nf0hbk9qz4qggwddxfyyyqy
title: '404'
desc: ''
updated: 1641426007206
created: 1641426007206
---


### 404

```python
from fastapi import FastAPI, Response, status, HTTPException

app = FastAPI()

@app.get("/posts/{id}")
def get_post(id: int, response: Response):
    post = find_post(id)
    if not post:
		raise HTTPException(status_code=status.HTTP_404_NOT_FOUND,
							detail=f"post with id: {id} was not found")
    return {"post_detail": post}
```
