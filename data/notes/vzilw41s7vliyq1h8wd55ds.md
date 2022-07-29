

- [Docs](https://docs.python-requests.org/en/master/)
- [GitHub](https://github.com/psf/requests)

```python
import requests

# Get API Request from Azure DevOps

r = requests.get(f"https://dev.azure.com/{organization}/{project}/_apis/wit/workitems?ids={ids}&api-version=6.1-preview.3", auth=(username, token))
#['Body'].read().decode('utf-8-sig')
print(r.status_code)
print(r.headers['content-type'])
print(r.encoding)
# print(r.text)
# r.json()["value"]
print(json.dumps(r.json(), indent=4))
```
