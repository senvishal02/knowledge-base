---
title: "Kubernetes Interview Q&A"
description: "Kubernetes architecture, workloads, and troubleshooting interview questions"
tags: [interview, kubernetes, architecture, troubleshooting]
---

# Kubernetes Interview Q&A

> **Kubernetes questions from basic architecture to advanced troubleshooting.**

!!! question "Q: Explain Kubernetes architecture"
    **Control Plane Components:**

    - `kube-apiserver` — REST API gateway for all cluster operations
    - `etcd` — Distributed key-value store for cluster state
    - `kube-scheduler` — Assigns pods to nodes based on constraints
    - `kube-controller-manager` — Runs control loops (ReplicaSet, Deployment, etc.)

    **Node Components:**

    - `kubelet` — Agent on each node that manages pod lifecycle
    - `kube-proxy` — Network proxy that maintains iptables rules
    - `Container Runtime` — CRI-compatible runtime (containerd, CRI-O)

!!! question "Q: How do you debug a pod stuck in CrashLoopBackOff?"
    ```bash
    # 1. Check pod events
    kubectl describe pod <name> -n <namespace>
    
    # 2. Check container logs
    kubectl logs <name> -n <namespace> --previous
    
    # 3. Check resource limits
    kubectl get pod <name> -o yaml | grep -A5 resources
    
    # 4. Exec into the container (if possible)
    kubectl exec -it <name> -- /bin/sh
    ```

---

*Continue adding questions as you prepare for interviews.*
