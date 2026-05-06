---
title: "CI/CD Interview Questions"
description: "CI/CD pipeline design, deployment strategies, and tool comparison interview questions"
tags: [interview, cicd, pipelines, deployment]
---

# CI/CD Interview Questions

> **CI/CD pipeline design and deployment strategy questions.**

## Pipeline Design

!!! question "Q: Design a CI/CD pipeline for a microservices application"
    A production-grade pipeline for microservices:

    ```
    1. Code Push → Trigger pipeline
    2. Lint & Static Analysis → SonarQube, ESLint
    3. Unit Tests → pytest, Jest
    4. Build Container Image → Docker multi-stage
    5. Security Scan → Trivy, Snyk
    6. Push to Registry → ECR, GHCR
    7. Deploy to Staging → Helm + ArgoCD
    8. Integration Tests → API tests, smoke tests
    9. Manual Approval (optional) → for production
    10. Deploy to Production → Canary/Blue-Green
    11. Post-deploy Validation → health checks, metrics
    ```

## Deployment Strategies

!!! question "Q: Compare Blue-Green, Canary, and Rolling deployments"
    | Strategy | Risk | Downtime | Rollback Speed | Cost |
    |---|---|---|---|---|
    | **Blue-Green** | Low | Zero | Instant | High (2x infra) |
    | **Canary** | Very Low | Zero | Fast | Medium |
    | **Rolling** | Medium | Zero | Slower | Low |
    | **Recreate** | High | Yes | Slow | Low |

---

*Continue adding questions as you prepare for interviews.*
