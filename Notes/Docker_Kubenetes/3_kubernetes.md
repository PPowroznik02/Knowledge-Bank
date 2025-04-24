# Kubernetes Overview

## What is Kubernetes?

Kubernetes is an open-source container orchestration platform that automates the deployment, scaling, and management of containerized applications.

---

## Key Concepts

### Stateless Application

An application that does not maintain any state between requests. Each request is treated independently. Typically used with **Deployment** resources.

### Deployment

A controller that manages stateless applications. It ensures that a specified number of pod replicas are running and updated at all times.

### StatefulSet

Used to manage **stateful** applications. It provides unique network identities and persistent storage for each pod, which is maintained across rescheduling.

### Persistent Volume Claim (PVC)

A request for storage by a user. It allows pods to claim persistent storage from a **PersistentVolume**.

### Storage Class

Defines types of storage (e.g., SSD, HDD) and determines how storage is dynamically provisioned.

### Pod

The smallest deployable unit in Kubernetes. A pod can contain one or more containers that share storage, network, and a specification.

### Node

A worker machine in Kubernetes. It may be a virtual or physical machine and runs the pods assigned to it.

---

## Common `kubectl` Commands

```bash
# Create or update resources from a manifest file
kubectl apply -f <manifest_file>

# Create new resources from a manifest file
kubectl create -f <manifest_file>

# Get a list of deployed resources (e.g., pods, deployments, services)
kubectl get <object>

# Get detailed information about a specific resource
kubectl describe <object> <name>

# List all pods
kubectl get pods

# Delete resources defined in a manifest file
kubectl delete -f <manifest_file>

# Scale a deployment to a specific number of replicas
kubectl scale deployment <deployment_name> --replicas=<number>

# Scale a StatefulSet to a specific number of replicas
kubectl scale statefulset <statefulset_name> --replicas=<number>

# Monitor a specific resource (watch for changes)
kubectl get <object> -w

# List all services
kubectl get services

# List all available storage classes
kubectl get sc

# List all persistent volume claims
kubectl get pvc

# List all persistent volumes
kubectl get pv

# View logs of a specific pod
kubectl logs <pod_name>
```
