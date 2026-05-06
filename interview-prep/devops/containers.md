---
title: "Container Interview Questions"
description: "Docker and container interview questions for DevOps roles"
tags: [interview, docker, containers, security]
---

# Container Interview Questions

> **Docker and containerisation questions for DevOps interviews.**

!!! question "Q: What is the difference between a container and a VM?"
    | Aspect | Container | VM |
    |---|---|---|
    | Isolation | Process-level (shared kernel) | Hardware-level (hypervisor) |
    | Size | MBs | GBs |
    | Startup | Seconds | Minutes |
    | Overhead | Minimal | Significant |
    | Portability | OCI standard | Hypervisor-dependent |

!!! question "Q: How do you optimise a Docker image?"
    1. Use multi-stage builds to separate build and runtime
    2. Use minimal base images (Alpine, distroless)
    3. Combine RUN layers to reduce image layers
    4. Use `.dockerignore` to exclude unnecessary files
    5. Order Dockerfile instructions by change frequency (least → most)
    6. Pin dependency versions for reproducibility
    7. Remove package manager caches in the same layer

---

*Continue adding questions as you prepare for interviews.*
