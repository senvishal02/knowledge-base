# 🚀 Self-Hosted Nextcloud on Docker (Home Server Guide)

Build your own **personal cloud storage** using **Nextcloud + Docker + Cloudflare Tunnel**.

👉 This setup allows you to:

- Use your **laptop as a home server**
- Attach an **external HDD/SSD** for storage
- Access files securely from anywhere
- Avoid port forwarding using Cloudflare Tunnel

---

## 🎯 Purpose

This project enables you to build a powerful self-hosted cloud solution with the following capabilities:

- 📁 **Personal Google Drive Alternative**  
  Store, manage, and access your files securely without relying on third-party services.

- 🔐 **Secure Private Cloud**  
  Full control over your data with enhanced privacy and security.

- 🏠 **Home Lab Storage Server**  
  Centralized storage for all your devices, ideal for home lab and self-hosting environments.

- ☁️ **Remote File Access System**  
  Access your files anytime, anywhere through a secure internet connection.

- 📱 **Automatic Phone Backup & Sync**  
  Seamlessly sync photos, videos, and documents from your mobile device for continuous backup.

- 💾 **Extend Device Storage**  
  Free up space on your phone or laptop by offloading files to your personal cloud.

- 🔄 **Cross-Device Synchronization**  
  Keep files synced across mobile, desktop, and tablet in real time.

- 🛡️ **Full Data Ownership & Control**  
  No vendor lock-in — your data stays private and fully under your control.

---

## 📦 Prerequisites

- Docker & Docker Compose
- Cloudflare account + domain added
- External storage (as required)

---

## 🧰 Tech Stack

| Component        | Purpose |
|----------------|--------|
| Nextcloud      | File storage & collaboration platform |
| MariaDB        | Database for Nextcloud |
| Redis          | Caching & performance improvement |
| Docker         | Containerization |
| Cloudflare Tunnel | Secure public access (no open ports) |

---

## 📂 Project Structure

```text
nextcloud/
├── docker-compose.yml 
└── volumes/            # (auto created)
    ├── db/             # Database storage (auto created)
    ├── cloudflared/    # Cloudflare data (auto created)    
    ├── nextcloud/      # Nextcloud data (auto created)
    └── redis/          # Redis persistence (auto created)
```


---

## 💾 External Storage Setup (Important)

Before starting containers:

👉 If using **External HDD/SSD**, you MUST mount it first.

*Example (Linux/macOS)*:

```bash
mount /dev/sdX $PWD/nextcloud/Volumes/
```

Then update paths in docker-compose.yml:
```bash
/Volumes/ExternalHDD/nextcloud/
```

## 🧱 1. Docker Setup

### 📄 Create Compose File

```yaml title="docker-compose.yml"
services:
  nextcloud:
    image: nextcloud:latest
    container_name: nextcloud
    ports:
      - "8080:80"
    volumes:
      - ./volumes/nextcloud:/var/www/html
    environment:
      - MYSQL_DATABASE=nextcloud
      - MYSQL_USER=nextcloud
      - MYSQL_PASSWORD=nextcloudpass
      - MYSQL_HOST=db
    depends_on:
      - db

  db:
    image: mariadb:10.6
    container_name: nextcloud-db
    environment:
      - MYSQL_ROOT_PASSWORD=rootpass
      - MYSQL_DATABASE=nextcloud
      - MYSQL_USER=nextcloud
      - MYSQL_PASSWORD=nextcloudpass
    volumes:
      - ./volumes/db:/var/lib/mysql

  redis:
    image: redis:7
    container_name: nextcloud-redis
    volumes:
      - ./volumes/redis:/data
```

### ▶️ Start Containers

```bash
docker-compose up -d
```

## 🌐 2. First-Time Setup

Open:

```bash
http://localhost:8080
```

**Create**:

- Admin username
- Password

--- 

## 🌍 3. Cloudflare Tunnel Setup

> ⚠️ **Important:**  
> Before continuing, make sure your domain is configured in Cloudflare.  
> 👉 [Click here to complete Cloudflare Setup](cloudflare-setup.md)

### 🔐 Login

```bash
docker run -it cloudflare/cloudflared:latest tunnel login
```
Output:
```text
2026-04-05T21:48:45Z INF You have successfully logged in.
If you wish to copy your credentials to a server, they have been saved to:
/home/nonroot/.cloudflared/cert.pem
```

### 📥 Save Credentials

```bash
docker run -it \
-v ./volumes/cloudflared:/home/nonroot/.cloudflared \
cloudflare/cloudflared:latest tunnel login
```

### 🧩 Create Tunnel

```bash
docker run -it \
-v ./volumes/cloudflared:/home/nonroot/.cloudflared \
cloudflare/cloudflared:latest tunnel create nextcloud
```

Output:
```text
Tunnel credentials written to /home/nonroot/.cloudflared/75xxxxxx-a3xx-43xx-9xxx-1xxxxxxxx3f1.json. cloudflared chose this file based on where your origin certificate was found. Keep this file secret. To revoke these credentials, delete the tunnel.

Created tunnel nextcloud-test with id 75xxxxxx-a3xx-43xx-9xxx-1xxxxxxxx3f1
```

This will create: 

```bash
./volumes/cloudflared/<TUNNEL_ID>.json
```

### ⚙️ Create Config File

```yaml title='./volumes/cloudflared/config.yml'
tunnel: <TUNNEL_ID>
credentials-file: /etc/cloudflared/<TUNNEL_ID>.json

ingress:
  - hostname: <cloud.yourdomain.com>
    service: http://nextcloud:80
  - service: http_status:404
```

### ➕ Add Cloudflare Service to Docker Compose

Append this to your docker-compose.yml:

```yaml title='docker-compose.yml'
  cloudflared:
    image: cloudflare/cloudflared:latest
    container_name: nextcloud-cloudflared
    command: tunnel --config /etc/cloudflared/config.yml run
    volumes:
      - ./volumes/cloudflared:/etc/cloudflared
    depends_on:
      - nextcloud
```

### ▶️ Start Cloudflare Containers

```bash
docker compose up -d
```

---

## 🌐 4. Create DNS Record

### 🚀 Option 1: Automatic Method

Run the following command to automatically create the DNS record:

```bash
docker run -it \
  -v $(pwd)/volumes/cloudflared:/home/nonroot/.cloudflared \
  cloudflare/cloudflared:latest \
  tunnel route dns nextcloud cloud.yourdomain.com
```
### ⚙️ Option 2: Manual Method (or Verification)

If you prefer to create the DNS record manually—or want to verify it—follow these steps:

1. Go to your **Cloudflare Dashboard**
2. Navigate to:  
   **DNS → Records**
3. Create a new record with the following details:

| Field  | Value                         |
|--------|------------------------------|
| Type   | CNAME                         |
| Name   | cloud (or any subdomain)      |
| Target | `TUNNEL_ID.cfargotunnel.com` |
| Proxy  | ✅ Proxied (Orange Cloud ON)  |

---

### ⚠️ Note

If you try to access the URL now, you may encounter a **Domain Trust Issue**.  
This is expected at this stage—continue with the next steps to resolve it.

---

## 🔐 5. Nextcloud Trusted Config

```bash
docker exec -it nextcloud php occ config:system:set overwritehost --value=nextcloud.yourdomain.com &&
docker exec -it nextcloud php occ config:system:set overwriteprotocol --value=https &&
docker exec -it nextcloud php occ config:system:set overwrite.cli.url --value=https://nextcloud.yourdomain.com &&

docker exec -it nextcloud php occ config:system:set trusted_domains 0 --value=nextcloud.yourdomain.com &&
docker exec -it nextcloud php occ config:system:set trusted_domains 1 --value=localhost &&

docker exec -it nextcloud php occ config:system:set trusted_proxies 0 --value=127.0.0.1 &&
docker exec -it nextcloud php occ config:system:set trusted_proxies 1 --value=172.17.0.0/16 &&

docker exec -it nextcloud php occ config:system:set forwarded_for_headers 0 --value=HTTP_X_FORWARDED_FOR &&
docker exec -it nextcloud php occ config:system:set forwarded_for_headers 1 --value=HTTP_CF_CONNECTING_IP
```

---

## ⚡ 6. Redis Performance Optimization

```bash
docker exec -it nextcloud php occ config:system:set memcache.local --value='\OC\Memcache\Redis' &&
docker exec -it nextcloud php occ config:system:set memcache.distributed --value='\OC\Memcache\Redis' &&
docker exec -it nextcloud php occ config:system:set memcache.locking --value='\OC\Memcache\Redis' &&
docker exec -it nextcloud php occ config:system:set redis host --value='redis' &&
docker exec -it nextcloud php occ config:system:set redis port --value='6379'
```

---

## ✅ 7. Fix Security & setup warnings

```bash
docker exec -u www-data nextcloud php occ config:system:set maintenance_window_start --type=integer --value=2 &&
docker exec -u www-data nextcloud php occ maintenance:repair --include-expensive &&
docker exec -u www-data nextcloud php occ config:system:set default_phone_region --value=IN
```

---

## ⚠️ Important Notes

- Always mount external disk before starting containers
- Keep tunnel credentials safe
- Use strong passwords
- Backup regularly

---

## ✅ Final Access
```bash
https://cloud.yourdomain.com
```
