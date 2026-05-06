---
title: "AWS CLI Cheatsheet"
description: "Essential AWS CLI commands for cloud operations"
tags: [cheatsheet, aws, cli]
---

# AWS CLI Cheatsheet


## EC2

```bash
aws ec2 describe-instances --filters "Name=tag:Name,Values=web*"
aws ec2 start-instances --instance-ids i-xxx
aws ec2 stop-instances --instance-ids i-xxx
```

## S3

```bash
aws s3 ls
aws s3 cp file.txt s3://bucket/
aws s3 sync ./dir s3://bucket/dir
aws s3 rm s3://bucket/file.txt
```

## IAM

```bash
aws iam list-users
aws iam list-roles
aws sts get-caller-identity
aws sts assume-role --role-arn arn:aws:iam::xxx:role/name --role-session-name session
```

## EKS

```bash
aws eks list-clusters
aws eks update-kubeconfig --name cluster-name --region region
```
