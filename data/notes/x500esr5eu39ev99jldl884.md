
## Tips

- consider each line of the docker a layer of the abstraction this comes into play in the next example.
- Docker files MUST start with `FROM` but after that you can also add data like:

```docker
FROM python:3.9.7
MAINTAINER Bryan Jenks bryan@bryanjenks.dev
```

- When you build your docker image from a docker file with [[s.containers.docker.cmd.build]] each command in the file create a new image and the layers are plastered on top, but each layer is cached so when you change things iteratively, only the changed items onward get re-ran. Essentially lazy loading.

## Base example of having to install all your dependencies and everything

Negates the utility of docker if the image is not just "good to go" but here's how to do this

---

```docker
FROM python:3.9.7
WORKDIR /usr/src/app
COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt
COPY . .
CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]
```

---

- `FROM python:3.9.7`
  - Specify what python version to run in the base image
  - "python" is the image
  - "3.9.7" is the version of that image
- `WORKDIR /usr/src/app`
  - "/usr/src" is a valid path in the image
  - "/app" is the path we want to tack on and create for our app code
- `COPY requirements.txt ./`
  - Grab the requirements file into the image
- `RUN pip install --no-cache-dir -r requirements.txt`
  - Install dependencies
- `COPY . .`
  - "." first dot is current directory, second "." is `WORKDIR`
  - Move our source code into the image
  - This is where layering comes into play, when you change source code files
    - The only thing that changed was source code so this step and below is what gets re-ran
  - Each layers results are cached, so when you change something it only re-runs steps where something has changed compared to the cached image layers.
    - Only changed source code? then only re-run the step where we copy over source code files
- `CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "8000"]`
  - The array of commands to run once the image is spun up
  - each array items is either a switch or a param
  - essentially any time you have a space between anything in the command that is when you make a separate item in the array for it.

At this point you can now create the image using [[s.containers.docker.cmd.build]]

## Security

Specify a `USER` in the docker file like `USER 1000` so that processes do not run as root and prevent potential security risk

## Multi-Stage

Reduce container size by not building on top of a big image

```docker
FROM golang:1.14.2-alpine3.11 AS builder
ENV GOPATH /go
WORKDIR /$GOPATH/src/croc-hunter/
COPY croc-hunter.go /go/src/croc-hunter/
RUN go get -d -v
RUN go build -o /go/bin/croc-hunter

FROM alpine:3.11 AS runtime
USER 1000
WORKDIR /app
COPY static/ static/
COPY --from=builder /go/bin/croc-hunter /app/croc-hunter
EXPOSE 8080
CMD [ "/app/croc-hunter" ]
```

## Dynamic Port exposure

you can set the docker file to use `EXPOSE ${PORT}` in the docker file and then pass in that value during the `docker run` command. It also helps to have the deployed code rely on the environmental variable as well so everything is dynamic based on the arguments fed to the container:

```bash
docker run -e PORT=3000 -p 3000:3000 --name croc-hunter croc-hunter-port:1
```


