---
title: "ML System Design"
description: "ML system design interview questions and patterns"
tags: [interview, mlops, system-design, ml-pipelines]
---

# ML System Design

> **End-to-end ML system design questions.**

!!! question "Q: Design an ML system for real-time fraud detection"
    Key components:
    
    - **Feature Store** — Pre-computed features with low-latency serving
    - **Model Training** — Offline batch training with experiment tracking
    - **Model Serving** — Real-time inference API (<50ms latency)
    - **Monitoring** — Data drift, model performance, prediction distribution
    - **Retraining** — Automated retraining pipeline triggered by drift alerts

---

*Continue adding ML system design patterns.*
