

## Path definitions for API End Points

<https://calmcode.io/til/fastapi-two-decorators.html>

> Let's consider a very basic FastAPI app that has a health endpoint.

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/health")
def get_health():
    return {"status": "alive"}

```

> This `/health` endpoint has one job: to return a response with status 200. It can serve as a signal that the service is healthy and this is typically used by cloud providers as a indication that a service might need a restart.
>
> Some services however, don't use `/health` but `/healthz` instead. So how might you implement this? You could add another route.

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/health")
def get_health():
    return {"status": "alive"}

@app.get("/healthz")
def get_health():
    return {"status": "alive"}

```

> But there's a simpler way, you can also just do this:

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/health")
@app.get("/healthz")
def get_health():
    return {"status": "alive"}

```

> You can totally stack decorators in Python, and FastAPI will just consider it another route that needs to be added.
>
> So you only need a single line of code. Neat!
