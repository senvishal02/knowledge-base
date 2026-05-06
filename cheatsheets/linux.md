---
title: "Linux Cheatsheet"
description: "Essential Linux commands for DevOps engineers"
tags: [cheatsheet, linux, commands]
---

# Linux Cheatsheet


## File Operations

```bash
# List files with details
ls -la

# Find files by name
find /path -name "*.log" -mtime -7

# Search file contents
grep -rn "pattern" /path/

# Disk usage
du -sh /path/*
df -h
```

## Process Management

```bash
# View processes
ps aux | grep process_name
top -bn1 | head -20

# Kill process
kill -9 PID
pkill -f process_name

# Background jobs
nohup command &
```

## Networking

```bash
# Check connectivity
ping -c 4 host
curl -I https://example.com

# Port checking
ss -tlnp
netstat -tlnp

# DNS
dig domain.com
nslookup domain.com
```

## User Management

```bash
# Add user
useradd -m -s /bin/bash username
passwd username

# Add to group
usermod -aG groupname username

# Switch user
su - username
sudo -u username command
```

## File Permissions

```bash
# Change permissions
chmod 755 file
chmod u+x script.sh

# Change ownership
chown user:group file
chown -R user:group directory/
```
