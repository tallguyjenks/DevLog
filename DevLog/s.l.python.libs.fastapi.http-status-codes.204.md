---
id: 56g7z9rzplmjfyuib2fpun3
title: '204'
desc: ''
updated: 1641426012593
created: 1641426012593
---


### 204

Cant delete something already deleted or doesnt exist and therefore cannot delete. No data returned

```python
@app.delete("/posts/{id}", status_code=status.HTTP_204_NO_CONTENT)
def delete_post(id: int):
    index = find_index_post(id)
    if index == None:
        raise HTTPException(status_code=status.HTTP_404_NOT_FOUND, detail=f"post with id: {id} does not exist")
    my_posts.pop(index)
    return Response(status_code=status.HTTP_204_NO_CONTENT)
```
