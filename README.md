# ICAP service with clamAV antivirus

This repository provides a kubernetes / docker / podman solution to run an ICAP service with ClamAV. 
This is designed for testing purpose only.

## What you’ll need
- kubernetes cluster. This was tested in [Microk8s](https://github.com/stanislaspiron/microk8s_awx/blob/main/microk8s/microk8s_install.md)
- [metallb](https://github.com/stanislaspiron/microk8s_awx/blob/main/microk8s/install_metallb.md) load balancer

# Building your own container image
You can build your own container image or use the one provided on Docker Hub.

[Build Docker image](docker/README.md)

# AWX custom Execution environment

1. [Deploy ICAP service in kubernetes](k8s/README.md)
# Addtionnal informations
This container accept RESPMOD and REQMOD for following services
- avscan
- srv_clamav
- virus_scan

Virus signature database is updated every hour.

# Logs
Following Logs are configured to write to stdout:
- C-ICAP ServerLog (istag is recomputed, virus detected, ...)
- ClamAV Updates status

To see Pod Logs, execute :

```
kubectl logs -f <pod name>
```
