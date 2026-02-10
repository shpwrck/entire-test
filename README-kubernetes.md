# Kubernetes Quick Reference

Kubernetes (k8s) is an open-source container orchestration platform for automating deployment, scaling, and management of containerized applications.

## Core Concepts

- **Pod** — Smallest deployable unit; one or more containers sharing network/storage
- **Deployment** — Manages replica sets and rolling updates for pods
- **Service** — Stable network endpoint to expose pods (ClusterIP, NodePort, LoadBalancer)
- **Namespace** — Logical isolation boundary within a cluster
- **ConfigMap / Secret** — Externalized configuration and sensitive data

## Common Commands

```sh
# Cluster info
kubectl cluster-info
kubectl get nodes

# Workloads
kubectl get pods -A
kubectl describe pod <name>
kubectl logs <pod> -f

# Deployments
kubectl apply -f deployment.yaml
kubectl rollout status deployment/<name>
kubectl scale deployment/<name> --replicas=3

# Services
kubectl get svc
kubectl expose deployment/<name> --port=80 --type=LoadBalancer

# Debugging
kubectl exec -it <pod> -- /bin/sh
kubectl top pods
```

## Minimal Deployment YAML

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: my-app
spec:
  replicas: 2
  selector:
    matchLabels:
      app: my-app
  template:
    metadata:
      labels:
        app: my-app
    spec:
      containers:
        - name: my-app
          image: my-app:latest
          ports:
            - containerPort: 8080
```

## Key Principles

- Declare desired state in YAML; Kubernetes reconciles actual state to match
- Use liveness and readiness probes for self-healing
- Set resource requests and limits to avoid noisy neighbors
- Use namespaces and RBAC to enforce least-privilege access
