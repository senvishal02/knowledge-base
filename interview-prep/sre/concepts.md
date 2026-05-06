---
title: "SRE Concepts & SLOs"
description: "SRE principles, error budgets, SLIs, SLOs, and SLAs interview questions"
tags: [interview, sre, slo, sli, error-budget]
---

# SRE Concepts & SLOs

> **Core SRE concepts tested in reliability engineering interviews.**

!!! question "Q: Explain the relationship between SLI, SLO, and SLA"
    - **SLI (Service Level Indicator):** A quantitative measure of service quality (e.g., request latency p99)
    - **SLO (Service Level Objective):** A target value for an SLI (e.g., p99 latency < 200ms)
    - **SLA (Service Level Agreement):** A contract with consequences if SLOs are not met

!!! question "Q: What is an error budget and how is it used?"
    Error budget = 1 - SLO target. For a 99.9% availability SLO, the error budget is 0.1% (~43 min/month). Teams can "spend" this budget on deployments and changes. When budget is exhausted, focus shifts to reliability.

---

*Continue adding questions as you prepare.*
