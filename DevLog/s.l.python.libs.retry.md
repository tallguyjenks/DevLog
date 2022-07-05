---
id: hb134d78yvqxwglmjt3v3o9
title: Retry
desc: ''
updated: 1657052945102
created: 1657052695313
---

<https://calmcode.io/shorts/retry.py.html>

Related to [[s.l.python.libs.fastapi]]

> The retry library has a single decorator that can tell the function to try again after failing. Here's how you can use it:

## Setup

```python
import random
from requests.exceptions import HTTPError

def pretend_request():
    if random.random() < 0.01:
        raise HTTPError("Something went wrong!")
    return {"status": "alive"}

# You'll likely hit an error
for i in range(500):
    pretend_request()
```

## Usage

```python
from retry import retry

@retry(tries=3, delay=0.1)
def pretend_request():
    if random.random() < 0.01:
        raise HTTPError("Something went wrong!")
    return {"status": "alive"}

# You'll likely hit an error
for i in range(500):
    pretend_request()
```

## Put it all toether

```python
import random
import logging
from requests.exceptions import HTTPError
from retry import retry

logging.basicConfig()

@retry(HTTPError, tries=10, delay=0.1, backoff=2)
def pretend_request():
    if random.random() < 0.1:
        raise rq.exceptions.HTTPError("Something went wrong!")
    return {"status": "alive"}

for i in range(100):
    pretend_request()

# >>> WARNING:retry.api:Something went wrong!, retrying in 0.1 seconds...
# >>> WARNING:retry.api:Something went wrong!, retrying in 0.2 seconds...
# >>> WARNING:retry.api:Something went wrong!, retrying in 0.4 seconds...
```

## Configuration

```python
import random
from retry import retry
from requests.exceptions import HTTPError


@retry(HTTPError, tries=3, delay=0.1)
def pretend_request():
    if random.random() < 0.01:
        raise HTTPError("Something went wrong!")
    return {"status": "alive"}

# Now, the function will only retry if detects a HTTPError. If you were to configure it to only respond to ValueError and TypeError then any other errors will be ignored.

@retry((ValueError, TypeError), tries=3, delay=0.1)
def pretend_request():
    if random.random() < 0.01:
        raise HTTPError("Something went wrong!")
    return {"status": "alive"}

# You'll likely hit an error again
for i in range(500):
    pretend_request()
```




