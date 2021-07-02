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

# Test ICAP container in Docker / Podman

```
podman run -d  -p 1344:1344  c-icap-container
```


# Addtionnal informations
This container accept RESPMOD and REQMOD for following services
- avscan
- srv_clamav
- virus_scan

Virus signature database is updated every hour.  
C-ICAP ServerLog (istag is recomputed, virus detected, ...) is configured to stdout. you can see it with:

## Podman
```
podman logs -f <container name>
```

## Docker
```
docker logs -f <container name>
```
