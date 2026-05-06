---
title: "Docker Cheatsheet"
description: "Essential Docker commands for container management"
tags: [cheatsheet, docker, containers]
---

# Docker Cheatsheet


## Container Lifecycle

```bash
docker run -d --name app -p 8080:80 nginx:alpine
docker ps -a
docker stop app
docker rm app
docker logs -f app
docker exec -it app /bin/sh
```

## Images

```bash
docker build -t myapp:v1 .
docker images
docker tag myapp:v1 registry/myapp:v1
docker push registry/myapp:v1
docker rmi image_id
docker system prune -a
```

## Docker Compose

```bash
docker compose up -d
docker compose down
docker compose logs -f service
docker compose ps
docker compose exec service sh
```
