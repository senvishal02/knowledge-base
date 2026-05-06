---
title: "Lab 02 — PersistentVolumes"
description: "Work with Kubernetes PersistentVolumes and PersistentVolumeClaims"
tags: [lab, kubernetes, storage, pv, pvc]
---

# Lab 02 — PersistentVolumes


!!! info "Lab Details"
    **Difficulty:** Beginner · **Duration:** 45 min · **Prerequisites:** Lab 01 complete

## Objective
Understand persistent storage in Kubernetes using PVs and PVCs.

## Key Concepts
- PersistentVolume (PV) — cluster-level storage resource
- PersistentVolumeClaim (PVC) — user request for storage
- StorageClass — dynamic provisioning
- Access modes: ReadWriteOnce, ReadOnlyMany, ReadWriteMany

## Steps

### 1. Create a PersistentVolume
```yaml
apiVersion: v1
kind: PersistentVolume
metadata:
  name: demo-pv
spec:
  capacity:
    storage: 1Gi
  accessModes:
    - ReadWriteOnce
  hostPath:
    path: /tmp/demo-pv
```

### 2. Create a PVC and mount in a Pod
```yaml
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: demo-pvc
spec:
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 500Mi
```

*Detailed walkthrough and validation steps to be expanded.*
