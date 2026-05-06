# 🧰 Kubernetes Lab Setup – Tools Installation

In this lesson, we will install all required tools for running Kubernetes locally.

---

# 🎯 Objective

By the end of this lab you will have:

- kubectl
- kind (Kubernetes in Docker)
- minikube (optional)
- helm
- docker

---

# 🖥️ System Requirements

Minimum:

- 8 GB RAM  
- 4 CPU cores  
- 20 GB free disk  

Recommended:

- 16 GB RAM  

---

# 🐳 Install Docker

## Ubuntu

```bash
sudo apt update
sudo apt install -y docker.io
sudo systemctl enable docker
sudo systemctl start docker
sudo usermod -aG docker $USER
```
Log out and log in again.
