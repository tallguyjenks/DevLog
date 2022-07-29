

## Create and Run in Venv or on server port

```bash
poetry init &&
poetry shell &&
poetry add fastapi[all]
```

After Code is setup and ready to run:

```bash
# runs the app in the main.py file with the --reload option so that
# changes when the file is saved are hot loaded into the running API service
# on the port where the API is listening

# assumes there is a python package
# . My_Repo_Name
# ├─── app/
# │    ├─── __init__.py
# │    └─── main.py
# │         └─── app()

uvicorn app.main:app --reload
```
