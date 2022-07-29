

- `Author:` ran-isenberg
- `Link:` <https://isenberg-ran.medium.com/reduce-your-python-code-complexity-with-this-simple-trick-7046b7c54e7a>
- `Publish Date:` 2021.07.01
- `Reviewed Date:` [[log.daily.2021.11.30]]

---

- A customer management system receives requests.
- ![alt](assets/images/Pasted_image_20211130095653.png)
- Each request type is a Python dictionary and all 4 are handled uniquely
  - ![alt](assets/images/Pasted_image_20211130095905.png)

```python
request1 = {
    "action": "create",
    "customer": "customer1",
}

request2 = {
    "action": "activate",
    "customer": "customer2",
}

request3 = {
    "action": "suspend",
    "customer": "customer2",
}

request4 = {
    "action": "delete",
    "customer": "customer2",
}

def function_handler(request: Dict[str, Any]) -> None:
    # handle request
```

90e9dc

```python
from typing import Any, Dict


def function_handler(request: Dict[str, Any]) -> None:
    action = request.get("action")
    customer_name = request.get("customer")
    # validate input
    
    if action == "create":
        _handle_create_request(customer_name)
    elif action == "activate":
        _handle_activate_request(customer_name)
    elif action == "suspend":
        _handle_suspend_suspend(customer_name)
    elif action == "delete":
        _handle_delete_request(customer_name)


def _handle_create_request(customer_name: str) -> None:
    # do something related to create
    return


def _handle_activate_request(customer_name: str) -> None:
    # do something related to activate
    return


def _handle_suspend_suspend(customer_name: str) -> None:
    # do something related to suspend
    return


def _handle_delete_request(customer_name: str) -> None:
    # do something related to delete
    return
```

df2a07

```python
from typing import Any, Dict

ACTION_MAPPING = {
    "create": _handle_create_request,
    "activate": _handle_activate_request,
    "suspend": _handle_suspend_suspend,
    "delete": _handle_delete_request,
}

def function_handler(request: Dict[str, Any]) -> None:
    action = request.get("action")
    customer_name = request.get("customer")
    # validate input
    _handle_request(action, customer_name)


def _handle_request(action: str, customer_name: str) -> None:
    action_handler = ACTION_MAPPING.get(action)
    # handle action
    action_handler(customer_name)


def _handle_create_request(customer_name: str) -> None:
    # do something related to create
    return


def _handle_activate_request(customer_name: str) -> None:
    # do something related to activate
    return


def _handle_suspend_suspend(customer_name: str) -> None:
    # do something related to suspend
    return


def _handle_delete_request(customer_name: str) -> None:
    # do something related to delete
    return
```

c90001

