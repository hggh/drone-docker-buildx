# DroneCI Docker buildx plugin

This DroneCI Plugin allows you to build multi arch docker images with DroneCI and buildx


## howto use it

```
steps:
  - name: publish
    image: jgescireum/buildx:latest
    settings:
      registry: hub.private.com
      platforms:
        - linux/amd64
        - linux/arm64
      tags:
        - hub.private.com/username/test:latest
    environment:
      PLUGIN_EXPERIMENTAL: true
      DOCKER_PASSWORD:
        from_secret: docker_password
      DOCKER_USERNAME:
        from_secret: docker_username
    when:
      event:
        - push
```


## build

```
go build -v -a -tags netgo -o release/linux/amd64/drone-docker-buildx ./cmd/drone-docker-buildx
```


## docker image

```
docker build -f docker/docker/Dockerfile.linux.amd64 -t jgescireum/buildx:latest .
docker push jgescireum/buildx:latest
```
