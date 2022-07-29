
```markdown
.
└───app
    │   database.py
    │   utils.py
    │   __main__.py
    │
    └───routers
            post.py
            user.py
```

using routers you can break apart your API code into separate modules

## In the submodules

```python
from fastapi import APIRouter

router = APIRouter()

# change the @app decorator from `@app` to `@router`
```

## In the main file

```python
from .routers import post, user

app.include_router(post.router)
```

this is like a [[s.l.cpp.funcs.header-file]] where all the code gets dumped into
that location. So this is a way of separating out the code to separate files
cleanly.
