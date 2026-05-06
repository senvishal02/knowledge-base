---
title: "Scripting & Automation Interview Questions"
description: "Bash and Python scripting interview questions for DevOps roles"
tags: [interview, scripting, bash, python, automation]
---

# Scripting & Automation Interview Questions

> **Scripting and automation questions for DevOps interviews.**

!!! question "Q: Write a bash script to find the top 5 processes by memory usage"
    ```bash
    #!/bin/bash
    echo "Top 5 processes by memory usage:"
    ps aux --sort=-%mem | head -6
    ```

!!! question "Q: How do you handle errors in bash scripts?"
    ```bash
    #!/bin/bash
    set -euo pipefail  # Exit on error, undefined vars, pipe failures
    trap "echo Error on line $LINENO" ERR  # Error handler
    ```

---

*Continue adding questions as you prepare for interviews.*
