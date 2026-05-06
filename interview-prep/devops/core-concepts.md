---
title: "DevOps Core Concepts — Interview Q&A"
description: "Essential DevOps concepts and interview questions"
tags: [interview, devops, concepts]
---

# DevOps Core Concepts — Interview Q&A

> **Fundamental DevOps concepts tested in every interview.**

## Key Topics

### What is DevOps?

!!! question "Q: Explain DevOps in your own words"
    DevOps is a cultural and technical practice that unifies software development (Dev) and IT operations (Ops) to shorten the development lifecycle while delivering features, fixes, and updates frequently and reliably. It emphasises automation, collaboration, continuous feedback, and iterative improvement.

    **Key pillars:** Culture, Automation, Measurement, Sharing (CAMS)

### CI/CD Philosophy

!!! question "Q: Difference between Continuous Integration, Delivery, and Deployment?"
    - **Continuous Integration (CI):** Developers merge code to a shared branch frequently, with automated builds and tests running on every merge
    - **Continuous Delivery (CD):** Every change that passes CI is automatically deployable to production, but deployment is a manual trigger
    - **Continuous Deployment:** Every change that passes all automated tests is deployed to production automatically — no human intervention

### Infrastructure as Code

!!! question "Q: Why is Infrastructure as Code important?"
    IaC treats infrastructure configuration as software — version controlled, tested, reviewed, and reproducible. Benefits include:

    - **Reproducibility** — identical environments every time
    - **Drift detection** — know when actual state diverges from desired state
    - **Audit trail** — Git history shows who changed what and when
    - **Speed** — provision entire environments in minutes
    - **Collaboration** — code reviews for infrastructure changes

### Configuration Management vs Orchestration

!!! question "Q: Difference between Ansible and Terraform?"
    - **Terraform** — Infrastructure provisioning and orchestration (declarative, state-managed)
    - **Ansible** — Configuration management and application deployment (procedural, agentless)
    - Terraform creates the servers; Ansible configures what runs on them
    - They are complementary, not competing tools

---

!!! tip "Interview Tip"
    Always relate concepts back to real production scenarios. Interviewers value practical experience over textbook definitions.
