# Kubernetes-Practice
This repository holding all the code which I am going to practice to learn kubernetes

# Kubernetes & Minikube Commands

A collection of commonly used Kubernetes (`kubectl`) and Minikube commands for managing Pods, inspecting resources, viewing logs, applying YAML configurations, and accessing containers.

## 1. Minikube Commands

### Check Kubernetes Client Version

```bash
kubectl version
```

### Check Minikube Cluster Status

```bash
minikube status
```

### Update Minikube Context

```bash
minikube update-context
```

### Start Minikube Cluster

```bash
minikube start
```

## 2. Get Kubernetes Resources

**Syntax:**

```bash
kubectl get <object>
```

**Examples:**

```bash
kubectl get pods
kubectl get nodes
kubectl get services
kubectl get deployments
```

### Get Additional Resource Information

**Syntax:**

```bash
kubectl get <object> -o wide
```

**Example:**

```bash
kubectl get pods -o wide
```

The `-o wide` option displays additional information, such as Pod IP addresses and node assignments.

## 3. Describe Kubernetes Resources

**Syntax:**

```bash
kubectl describe <object> <object-name>
```

**Example:**

```bash
kubectl describe pod testpod
```

### Alternative Syntax

```bash
kubectl describe <object>/<object-name>
```

**Example:**

```bash
kubectl describe pod/testpod
```

Displays detailed information about the resource, including configuration, status, conditions, and events.

## 4. Apply YAML Configuration

**Syntax:**

```bash
kubectl apply -f <file.yml>
```

**Example:**

```bash
kubectl apply -f file.yml
```

Creates or updates Kubernetes resources using a YAML configuration file.

## 5. View Container Logs

### Follow Pod Logs

**Syntax:**

```bash
kubectl logs -f <pod-name>
```

**Example:**

```bash
kubectl logs -f testpod
```

The `-f` option continuously streams the logs.

### View Logs of a Specific Container

**Syntax:**

```bash
kubectl logs -f <pod-name> -c <container-name>
```

**Example:**

```bash
kubectl logs -f testpod -c c00
```

Useful when a Pod contains multiple containers.

## 6. Delete Kubernetes Resources

### Delete a Specific Resource

**Syntax:**

```bash
kubectl delete <object> <object-name>
```

**Example:**

```bash
kubectl delete pod testpod
```

### Delete Resources Using YAML

**Syntax:**

```bash
kubectl delete -f <file.yml>
```

**Example:**

```bash
kubectl delete -f file.yml
```

## 7. Execute Commands Inside Containers

### Execute a Single Command

**Syntax:**

```bash
kubectl exec <pod-name> -c <container-name> -- <command>
```

**Example:**

```bash
kubectl exec testpod -c c00 -- hostname
```

Executes the `hostname` command inside the specified container.

### Access Container Using Bash

**Syntax:**

```bash
kubectl exec -it <pod-name> -c <container-name> -- /bin/bash
```

**Example:**

```bash
kubectl exec -it testpod -c c00 -- /bin/bash
```

### Access Container Using Shell

**Syntax:**

```bash
kubectl exec -it <pod-name> -c <container-name> -- /bin/sh
```

**Example:**

```bash
kubectl exec -it testpod -c c00 -- /bin/sh
```

**Important:**
- `-i` keeps standard input open.
- `-t` allocates a terminal.
- `-c` specifies the container inside the Pod.
- `/bin/bash` requires Bash to be installed inside the container.
- `/bin/sh` is commonly available in lightweight images such as Alpine.

---

## 8. Quick Reference

| Task | Command |
|---|---|
| Check Kubernetes version | `kubectl version` |
| Check Minikube status | `minikube status` |
| Update context | `minikube update-context` |
| Start cluster | `minikube start` |
| List Pods | `kubectl get pods` |
| List resources with details | `kubectl get pods -o wide` |
| Describe Pod | `kubectl describe pod testpod` |
| Apply YAML | `kubectl apply -f file.yml` |
| View Pod logs | `kubectl logs -f testpod` |
| View container logs | `kubectl logs -f testpod -c c00` |
| Delete Pod | `kubectl delete pod testpod` |
| Delete using YAML | `kubectl delete -f file.yml` |
| Execute command | `kubectl exec testpod -c c00 -- hostname` |
| Enter Bash | `kubectl exec -it testpod -c c00 -- /bin/bash` |
| Enter Shell | `kubectl exec -it testpod -c c00 -- /bin/sh` |

**Note:** Replace `testpod`, `c00`, and `file.yml` with your actual Pod name, container name, and YAML filename.
