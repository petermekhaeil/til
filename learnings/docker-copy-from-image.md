# Docker: Copy files from another image

`COPY --from` is used for [mulit-stage builds](https://docs.docker.com/build/building/multi-stage/) and it is used to copy from another image, either by referencing a local image name or a tag available on a Docker registry. 

```docker
COPY --from=nginx:latest /etc/nginx/nginx.conf /nginx.conf
```

It can also be used for copying from stages created earlier in the Dockerfile:

```docker
# stage 1
FROM alpine as git
RUN apk add git

# stage 2
FROM git as fetch
WORKDIR /repo
RUN git clone https://github.com/your/repository.git .

# stage 3
FROM nginx as site
COPY --from=fetch /repo/docs/ /usr/share/nginx/html
```
