
```bash
docker exec -it fastapi_api bash
```

- Enters `docker` interactive mode (`-it`) on image named `fastapi_api` and runs the command `bash` for the interactive session
- `bash` overrides the defaul command of the docker file with is usually the `CMD` to start the image
