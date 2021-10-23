

## build

```
go build -v -a -tags netgo -o release/linux/amd64/drone-docker-buildx ./cmd/drone-docker-buildx
```


## docker image

```
docker build -f docker/docker/Dockerfile.linux.amd64 -t jgescireum/buildx:latest .
docker push jgescireum/buildx:latest
```
