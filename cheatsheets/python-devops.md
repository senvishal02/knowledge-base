---
title: "Python (DevOps) Cheatsheet"
description: "Python patterns for DevOps automation"
tags: [cheatsheet, python, devops, boto3]
---

# Python (DevOps) Cheatsheet


## File Operations

```python
import json, yaml, os

# Read JSON
with open("config.json") as f:
    data = json.load(f)

# Read YAML
with open("config.yaml") as f:
    data = yaml.safe_load(f)

# Environment variables
value = os.getenv("KEY", "default")
```

## Subprocess

```python
import subprocess

result = subprocess.run(
    ["kubectl", "get", "pods", "-o", "json"],
    capture_output=True, text=True, check=True
)
data = json.loads(result.stdout)
```

## Boto3 (AWS)

```python
import boto3

ec2 = boto3.client("ec2")
instances = ec2.describe_instances()

s3 = boto3.client("s3")
s3.upload_file("file.txt", "bucket", "key")
```

## HTTP Requests

```python
import requests

resp = requests.get("https://api.example.com/data", headers={"Authorization": "Bearer token"})
resp.raise_for_status()
data = resp.json()
```
