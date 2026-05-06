---
title: "Linux for DevOps Engineers"
description: "Master Linux from fundamentals to advanced system administration — the foundation of every DevOps and Cloud engineering role."
icon: material/linux
tags: [linux, sysadmin, shell-scripting, devops-fundamentals]
---

# :material-linux: Linux for DevOps Engineers

<div class="course-stats" markdown>
⏱️ **~14 hours** &nbsp;·&nbsp; 📚 **8 modules** &nbsp;·&nbsp; 🔬 **3 labs** &nbsp;·&nbsp; 🎓 **Beginner → Advanced**
</div>

!!! abstract "Course Overview"
    Linux is the backbone of every cloud infrastructure, container runtime, and CI/CD system.
    This course takes you from first-principles command-line confidence through to production-grade
    system administration, shell automation, and performance tuning.

---

## Learning Path

<div class="course-path-row" markdown>
🟢 Beginner → 🟡 Intermediate → 🔴 Advanced
</div>

```mermaid
graph LR
    A[Introduction] --> B[File System]
    B --> C[Users & Permissions]
    C --> D[Processes & Jobs]
    D --> E[Networking]
    E --> F[Shell Scripting]
    F --> G[Sysadmin]
    G --> H[Performance Tuning]
```

---

## Prerequisites

- [ ] Basic computer literacy (create files, install software)
- [ ] Access to a Linux VM, WSL2, or a cloud instance
- [ ] Any terminal emulator

---

## Complete Syllabus

### :material-numeric-1-circle: Phase 1 — Core Fundamentals

| Module | Topic | Level |
|--------|-------|-------|
| [01 — Introduction](01-introduction.md) | History, distros, setup, CLI basics | 🟢 Beginner |
| [02 — File System & Navigation](02-filesystem.md) | FHS, ls/cd/find/grep, inodes | 🟢 Beginner |
| [03 — Users & Permissions](03-permissions.md) | chmod, chown, sudo, ACLs | 🟢 Beginner |

### :material-numeric-2-circle: Phase 2 — System Management

| Module | Topic | Level |
|--------|-------|-------|
| [04 — Processes & Jobs](04-processes.md) | ps, top, kill, systemd, cron | 🟡 Intermediate |
| [05 — Networking Basics](05-networking.md) | ip, ss, netstat, DNS, firewalls | 🟡 Intermediate |
| [07 — System Administration](07-sysadmin.md) | Package managers, services, logs | 🟡 Intermediate |

### :material-numeric-3-circle: Phase 3 — Advanced Skills

| Module | Topic | Level |
|--------|-------|-------|
| [06 — Shell Scripting](06-shell-scripting.md) | Bash scripting, functions, error handling | 🔴 Advanced |
| [08 — Performance Tuning](08-performance.md) | vmstat, iostat, profiling, tuning | 🔴 Advanced |

---

## Hands-On Labs

- [:material-flask-outline: Lab: Deploy a Stateless App on Linux](../../labs/kubernetes-labs/lab-01-stateless-app.md)
- [:material-flask-outline: Lab: Docker Networking Deep Dive](../../labs/docker-labs/lab-02-networking.md)
- [:material-flask-outline: Lab: Multi-stage Docker Builds](../../labs/docker-labs/lab-01-multistage.md)

---

## Quick References

[:material-lightning-bolt: Linux Cheatsheet](../../cheatsheets/linux.md){ .md-button }
[:material-lightning-bolt: Bash Scripting Cheatsheet](../../cheatsheets/bash.md){ .md-button }
[:material-help-circle: Linux Interview Questions](../../interview-prep/devops/core-concepts.md){ .md-button }
[:material-map: DevOps Engineer Roadmap](../../roadmap/devops-roadmap.md){ .md-button }

---

## Interview Preparation

!!! tip "Key Topics for Linux Interviews"
    - Explain `chmod 755` vs `chmod 644`
    - How does `systemd` differ from `init`?
    - What is a zombie process?
    - Describe the Linux boot process
    - How do you debug high CPU on a production server?

[:material-help-circle: Full DevOps Interview Prep](../../interview-prep/devops/index.md){ .md-button .md-button--primary }

---

!!! success "Start Here"
    Begin your Linux journey → [01 — Introduction to Linux](01-introduction.md)
