---
title: "MLOps Engineering"
description: "End-to-end MLOps — ML pipelines, model registries, serving, monitoring, Kubeflow, MLflow, and LLMOps."
icon: material/robot-outline
tags: [mlops, kubeflow, mlflow, llmops, model-serving, feature-store]
---

# :material-robot-outline: MLOps Engineering

<div class="course-stats" markdown>
⏱️ **~24 hours** &nbsp;·&nbsp; 📚 **9 modules** &nbsp;·&nbsp; 🔬 **5 labs** &nbsp;·&nbsp; 🎓 **Intermediate → Advanced**
</div>

!!! abstract "Course Overview"
    MLOps bridges the gap between ML research and production systems. This course covers the
    full lifecycle — from experiment tracking and pipeline orchestration to model serving,
    monitoring, feature stores, and LLMOps at scale.

---

## Learning Path

<div class="course-path-row" markdown>
🟡 Intermediate → 🔴 Advanced
</div>

```mermaid
graph LR
    A[MLOps Principles] --> B[ML Pipelines]
    B --> C[Model Registry]
    C --> D[Model Serving]
    D --> E[Feature Stores]
    E --> F[ML Monitoring]
    F --> G[Kubeflow]
    G --> H[MLflow]
    H --> I[LLMOps]
```

---

## Prerequisites

- [ ] Python fundamentals
- [ ] Basic Docker and Kubernetes knowledge
- [ ] Familiarity with ML concepts (training, evaluation)

---

## Complete Syllabus

### :material-numeric-1-circle: Phase 1 — Foundations

| Module | Topic | Level |
|--------|-------|-------|
| [01 — MLOps Principles](01-principles.md) | DevOps for ML, maturity model, tooling landscape | 🟡 Intermediate |
| [02 — ML Pipelines](02-pipelines.md) | Pipeline design, orchestration, reproducibility | 🟡 Intermediate |
| [03 — Model Registry & Versioning](03-registry.md) | Model lineage, staging, promotion workflows | 🟡 Intermediate |

### :material-numeric-2-circle: Phase 2 — Production

| Module | Topic | Level |
|--------|-------|-------|
| [04 — Model Serving & APIs](04-serving.md) | REST serving, BentoML, TorchServe, batching | 🔴 Advanced |
| [05 — Feature Stores](05-feature-stores.md) | Feast, Tecton, online vs offline serving | 🔴 Advanced |
| [06 — ML Monitoring & Drift](06-monitoring.md) | Data drift, model decay, Evidently, Prometheus | 🔴 Advanced |

### :material-numeric-3-circle: Phase 3 — Platforms & LLMs

| Module | Topic | Level |
|--------|-------|-------|
| [07 — Kubeflow](07-kubeflow.md) | Kubeflow Pipelines, KServe, Katib | 🔴 Advanced |
| [08 — MLflow](08-mlflow.md) | Experiment tracking, model registry, deployment | 🔴 Advanced |
| [09 — LLMOps](09-llmops.md) | RAG pipelines, fine-tuning, LLM observability | 🔴 Advanced |

---

## Hands-On Labs

- [:material-flask-outline: Lab 01 — MLflow Tracking Server](../../labs/mlops-labs/lab-01-mlflow.md)
- [:material-flask-outline: Lab 02 — Kubeflow Pipelines](../../labs/mlops-labs/lab-02-kubeflow.md)
- [:material-flask-outline: Lab 03 — Model Serving with BentoML](../../labs/mlops-labs/lab-03-bentoml.md)
- [:material-flask-outline: Lab 04 — Feature Store with Feast](../../labs/mlops-labs/lab-04-feast.md)
- [:material-flask-outline: Lab 05 — LLM API Deployment](../../labs/mlops-labs/lab-05-llm-api.md)

---

## Real-World Projects

- [:material-rocket-launch: End-to-End ML Pipeline on Kubernetes](../../projects/mlops-projects/ml-pipeline-k8s.md)
- [:material-robot: LLMOps Platform (RAG + Monitoring)](../../projects/mlops-projects/llmops-platform.md)
- [:material-api: Real-time Model Inference API](../../projects/mlops-projects/inference-api.md)

---

## Quick References

[:material-help-circle: MLOps Interview Q&A](../../interview-prep/mlops/index.md){ .md-button }
[:material-map: MLOps Engineer Roadmap](../../roadmap/mlops-roadmap.md){ .md-button }

---

!!! success "Start Here"
    Begin with the fundamentals → [01 — MLOps Principles](01-principles.md)
