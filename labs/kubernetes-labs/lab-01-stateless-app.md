---
title: "Lab 01 — Deploy a Stateless App"
description: "Deploy a stateless web application on Kubernetes"
tags: [lab, kubernetes, deployment, beginner]
---

# Lab 01 — Deploy a Stateless App


!!! info "Lab Details"
    **Difficulty:** Beginner · **Duration:** 30 min · **Prerequisites:** kubectl, local K8s cluster

## Objective
Deploy a simple Nginx web server on Kubernetes using a Deployment and expose it via a Service.

## What You Will Learn
- Creating Kubernetes Deployments
- Exposing applications with Services (ClusterIP, NodePort)
- Scaling replicas
- Rolling updates and rollbacks

## Steps

### 1. Create the Deployment

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-demo
  labels:
    app: nginx-demo
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx-demo
  template:
    metadata:
      labels:
        app: nginx-demo
    spec:
      containers:
      - name: nginx
        image: nginx:1.25-alpine
        ports:
        - containerPort: 80
        resources:
          requests:
            cpu: 50m
            memory: 64Mi
          limits:
            cpu: 100m
            memory: 128Mi
```

```bash
kubectl apply -f deployment.yaml
kubectl get pods -l app=nginx-demo
```

### 2. Expose via Service

```bash
kubectl expose deployment nginx-demo --type=NodePort --port=80
kubectl get svc nginx-demo
```

### 3. Scale and Update

```bash
# Scale to 5 replicas
kubectl scale deployment nginx-demo --replicas=5

# Rolling update
kubectl set image deployment/nginx-demo nginx=nginx:1.26-alpine

# Rollback
kubectl rollout undo deployment/nginx-demo
```

## Validation

```bash
kubectl rollout status deployment/nginx-demo
kubectl get pods -l app=nginx-demo -o wide
```

## Clean Up

```bash
kubectl delete deployment nginx-demo
kubectl delete svc nginx-demo
```

---

[:octicons-arrow-right-24: Next Lab: PersistentVolumes](lab-02-pv-pvc.md){ .md-button }
