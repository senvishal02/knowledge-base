---
title: "System Design for SRE"
description: "System design interview questions focused on reliability and scalability"
tags: [interview, sre, system-design, distributed-systems]
---

# System Design for SRE

> **System design questions with a reliability engineering lens.**

!!! question "Q: Design a highly available web application"
    Key considerations:
    
    - **Multi-AZ deployment** with load balancing
    - **Auto-scaling** based on CPU/request metrics
    - **Database replication** with failover
    - **CDN** for static assets
    - **Health checks** at every layer
    - **Circuit breakers** for downstream dependencies
    - **Graceful degradation** for non-critical features

---

*Continue adding system design patterns.*
