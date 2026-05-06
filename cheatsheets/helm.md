---
title: "Helm Cheatsheet"
description: "Essential Helm commands for Kubernetes package management"
tags: [cheatsheet, helm, kubernetes]
---

# Helm Cheatsheet


## Repository

```bash
helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo update
helm search repo nginx
```

## Install/Upgrade

```bash
helm install release-name chart --namespace ns --create-namespace
helm upgrade release-name chart -f values.yaml
helm upgrade --install release-name chart  # Install or upgrade
helm rollback release-name revision
helm uninstall release-name
```

## Inspect

```bash
helm list -A
helm status release-name
helm history release-name
helm get values release-name
helm template chart -f values.yaml  # Render locally
```
