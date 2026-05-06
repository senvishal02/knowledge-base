---
title: "Lab 01 — Multi-stage Builds"
description: "Optimise Docker images with multi-stage builds"
tags: [lab, docker, multi-stage, optimisation]
---

# Lab 01 — Multi-stage Builds


!!! info "Lab Details"
    **Difficulty:** Beginner · **Duration:** 30 min

## Objective
Build optimised container images using multi-stage Dockerfiles to reduce image size by 80%+.

## Example Multi-stage Dockerfile

```dockerfile
# Stage 1: Build
FROM golang:1.22-alpine AS builder
WORKDIR /app
COPY . .
RUN CGO_ENABLED=0 go build -o server .

# Stage 2: Runtime
FROM alpine:3.19
RUN apk --no-cache add ca-certificates
COPY --from=builder /app/server /server
EXPOSE 8080
CMD ["/server"]
```

*Detailed walkthrough to be expanded.*
