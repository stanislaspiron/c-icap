# ICAP service with clamAV antivirus

This repository provides a kubernetes / docker / podman solution to run an ICAP service with ClamAV. 
This is designed for testing purpose only.

## What you’ll need (not tested with other microk8s specifications)
- An Ubuntu 20.04 LTS environment to run the commands
- At least 60G of disk space and 8G of memory are recommended
- An internet connection


# Building your own container image
You can build your own container image or use the one provided on Docker Hub.

[Build Docker image](docker/README.md)

# AWX custom Execution environment

1. [Deploy ICAP service in kubernetes](k8s/README.md)

## Addtionnal informations
This container accept RESPMOD and REQMOD for following services
- avscan
- srv_clamav
- virus_scan

Virus signature database is updated every hour
