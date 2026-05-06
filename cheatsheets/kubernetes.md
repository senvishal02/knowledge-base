---
title: "Kubernetes Cheatsheet"
description: "Essential kubectl commands for cluster management"
tags: [cheatsheet, kubernetes, kubectl]
---

# Kubernetes Cheatsheet


## Core Commands

```bash
# Get resources
kubectl get pods -A
kubectl get svc,deploy,rs -n namespace
kubectl get nodes -o wide

# Describe
kubectl describe pod pod-name -n namespace

# Logs
kubectl logs pod-name -n namespace -f --tail=100
kubectl logs pod-name -c container-name

# Exec
kubectl exec -it pod-name -n namespace -- /bin/sh

# Apply/Delete
kubectl apply -f manifest.yaml
kubectl delete -f manifest.yaml
```

## Debugging

```bash
# Events
kubectl get events --sort-by=.metadata.creationTimestamp

# Resource usage
kubectl top pods -n namespace
kubectl top nodes

# Port forward
kubectl port-forward svc/service-name 8080:80

# Debug pod
kubectl run debug --rm -it --image=busybox -- /bin/sh
```

## RBAC

```bash
kubectl auth can-i create pods --as=user
kubectl get clusterroles
kubectl get rolebindings -n namespace
```
