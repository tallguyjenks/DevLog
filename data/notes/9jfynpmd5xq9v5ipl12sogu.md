
Specifying tags in the router object makes the documentation for granularly
defined and easier to read.

```python
router = APIRouter(
    prefix='/posts',
    tags='posts'
)
``` 

results in something like this:

![FastAPI tags](/assets/images/2022-01-11-10-22-42.png)
