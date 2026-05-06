---
title: "Terraform & Infrastructure as Code"
description: "Master Terraform from HCL basics to multi-cloud modules, remote state, Terragrunt, CI/CD, and Terratest."
icon: material/terraform
tags: [terraform, iac, terragrunt, aws, modules, ci-cd]
---

# :material-terraform: Terraform & Infrastructure as Code

<div class="course-stats" markdown>
⏱️ **~18 hours** &nbsp;·&nbsp; 📚 **7 modules** &nbsp;·&nbsp; 🔬 **5 labs** &nbsp;·&nbsp; 🎓 **Beginner → Advanced**
</div>

!!! abstract "Course Overview"
    Terraform is the industry-standard IaC tool for provisioning cloud infrastructure.
    This course covers everything from HCL fundamentals to enterprise-grade module design,
    remote state management, Terragrunt DRY patterns, and automated testing with Terratest.

---

## Learning Path

<div class="course-path-row" markdown>
🟢 Beginner → 🟡 Intermediate → 🔴 Advanced
</div>

---

## Complete Syllabus

| Module | Topic | Level |
|--------|-------|-------|
| [01 — HCL Fundamentals](01-hcl.md) | Providers, resources, variables, outputs, locals | 🟢 Beginner |
| [02 — State Management](02-state.md) | Local vs remote state, S3 backend, locking | 🟡 Intermediate |
| [03 — Modules](03-modules.md) | Reusable modules, versioning, registry | 🟡 Intermediate |
| [04 — Terragrunt](04-terragrunt.md) | DRY patterns, environments, dependency graph | 🔴 Advanced |
| [05 — CI/CD with Terraform](05-cicd.md) | GitHub Actions, Atlantis, plan/apply gates | 🔴 Advanced |
| [06 — Testing with Terratest](06-testing.md) | Unit tests, integration tests, Go-based testing | 🔴 Advanced |
| [07 — Multi-cloud Patterns](07-multicloud.md) | AWS + Azure + GCP, workspace strategies | 🔴 Advanced |

---

## Hands-On Labs

- [:material-flask-outline: Lab 01 — AWS VPC with Terraform](../../labs/terraform-labs/lab-01-vpc.md)
- [:material-flask-outline: Lab 02 — Modules & Reuse](../../labs/terraform-labs/lab-02-modules.md)
- [:material-flask-outline: Lab 03 — Remote State (S3 + DynamoDB)](../../labs/terraform-labs/lab-03-remote-state.md)
- [:material-flask-outline: Lab 04 — Terragrunt Patterns](../../labs/terraform-labs/lab-04-terragrunt.md)
- [:material-flask-outline: Lab 05 — Drift Detection](../../labs/terraform-labs/lab-05-drift.md)

---

## Quick References

[:material-lightning-bolt: Terraform Cheatsheet](../../cheatsheets/terraform.md){ .md-button }
[:material-map: DevOps Engineer Roadmap](../../roadmap/devops-roadmap.md){ .md-button }
[:material-map: Platform Engineering Roadmap](../../roadmap/platform-engineering-roadmap.md){ .md-button }

---

!!! success "Start Here"
    Begin with HCL → [01 — HCL Fundamentals](01-hcl.md)
