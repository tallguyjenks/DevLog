
- `URL:` <https://takacsmark.com/dockerfile-tutorial-by-example-dockerfile-best-practices-2018/>
    - <https://youtu.be/6Er8MAvTWlI>
    - <https://youtu.be/ZcMr4G5DH7c>
- `Author:` Márk Takács

- Docker files MUST start with `FROM` but after that you can also add data like:

```docker
FROM python:3.9.7
MAINTAINER Bryan Jenks bryan@bryanjenks.dev
```

- When you build your docker image from a docker file with [[s.containers.docker.cmd.build]] each command in the file create a new image and the layers are plastered on top, but each layer is cached so when you change things iteratively, only the changed items onward get re-ran. Essentially lazy loading.
