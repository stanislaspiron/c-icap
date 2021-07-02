# Kubernetes deployement for c-icap container

**Note:** This configuration is designed for testing purpose only.

## Deployment configuration file

```
kind: Deployment
apiVersion: apps/v1
metadata:
  name: c-icap
spec:
  replicas: 2
  selector:
    matchLabels:
      name: c-icap
  template:
    metadata:
      name: c-icap
      labels:
        name: c-icap
    spec:
      containers:
        - name: c-icap
          image: 'docker.io/stan314o/c-icap-container:1.0'
          ports:
            - containerPort: 1344
              protocol: TCP
```

Install the deployment:

```
kubectl apply -f k8s/01-deployment.yml
```

## Load balancer service configuration
This service requires metallb load balancer.

```
---
kind: Service
apiVersion: v1
metadata:
  name: lb-c-icap
  annotations:
    metallb.universe.tf/allow-shared-ip: 'true'
spec:
  ports:
    - name: 'radius-acct'
      protocol: TCP
      port: 1344
      targetPort: 1344
  selector:
    name: c-icap
  type: LoadBalancer
  loadBalancerIP: 192.168.1.200
```

Install the service:

```
kubectl apply -f k8s/02-services.yml
```
