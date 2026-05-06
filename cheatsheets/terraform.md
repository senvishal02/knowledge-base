---
title: "Terraform Cheatsheet"
description: "Essential Terraform CLI commands"
tags: [cheatsheet, terraform, iac]
---

# Terraform Cheatsheet


## Workflow

```bash
terraform init
terraform plan -out=tfplan
terraform apply tfplan
terraform destroy
```

## State

```bash
terraform state list
terraform state show resource.name
terraform state mv old.name new.name
terraform state rm resource.name
terraform import resource.name id
```

## Workspace

```bash
terraform workspace list
terraform workspace new dev
terraform workspace select prod
```

## Debugging

```bash
TF_LOG=DEBUG terraform plan
terraform validate
terraform fmt -recursive
terraform graph | dot -Tpng > graph.png
```
