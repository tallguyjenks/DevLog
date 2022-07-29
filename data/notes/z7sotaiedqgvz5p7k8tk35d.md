

```python
from fastapi import FastAPI
from fastapi.testclient import TestClient
from app.main import ap
import pytest

client = TestClient(app)

def test_root():
    result = client.get('/')
    print(result.json().get('message'))
    assert result.json().get('message') == 'Hello World'
    assert result.status_code == 200
    # return {"msg": "Hello World"}

def test_create_user():
    result = client.post("/users/", json={"email": "john.doe@gmail.com","password": "password123"})
    # print(result.json().get('message'))
    print(result.json())
    assert result.json().get('email') == "john.doe@gmail.com"
    assert result.status_code == 201

```
