# c-icap container sources for Podman, Docker and kubernetes

**Note:** This container is designed for testing purpose only.

To build image and push to docker Hub, use following commands:

## Podman
```
podman build -t c-icap-container .
podman tag c-icap-container docker.io/stan314o/c-icap-container:1.0
podman push docker.io/stan314o/c-icap-container:1.0
```

## Docker 
Note : same command arguments as podman with docker comand name
```
docker build -t c-icap-container .
docker tag c-icap-container docker.io/stan314o/c-icap-container:1.0
docker push docker.io/stan314o/c-icap-container:1.0
```

