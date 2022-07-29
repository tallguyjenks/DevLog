
## Configuration File

`docker-compose.yml`

```yml
version: "3"
services:
  api:
    image: tallguyjneks/<hub-repo-name>:<optional-tag-name> # instead of build if this was a production env
    build: . # where is the thing im building
    depends_on: # builds dependencies before main containers
      - postgres
    ports:
      - 8000:8000 # <port on localhost>:<port on container
    volumes:
      - ./app:/usr/src/app:ro # makes it so docker can be aware of changes between a linked directory and `ro` means read only so docker cant change the files
    command: uvicorn app.main:app --host 0.0.0.0 --port 8000 --reload # overrides default command for the image when ran
    env_file:
      - ./.env
    # ^^^ OR vvv
    environment:
      - DATABASE_HOSTNAME=postgres # docker compose uses its own network dns so you can specify a name of another container instead of the ip address
      - DATABASE_PORT=5432 # you can either list them out or point docker to a .env file
  postgres:
    image: postgres
    environment:
      - POSTGRES_PASSWORD=password123
      - POSTGRES_DB=fastapi
    volumes: # data is transient in the image so you need to have a place to have permanently stored data
      - postgre-db: /var/lib/postgresql/data
volumes:
  postgres-db:
```

## Tips

- having 2 files for a **dev** and a **prod** environment
- no using `--reload` in production code because the code shouldn't be changing
- port [[n.port.80]] on local host so that you can view in web browser
- on linux the `environment:` values can use linux variable accessors `${DATABASE_HOSTNAME}`
