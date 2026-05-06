---
title: "Ansible Cheatsheet"
description: "Essential Ansible commands and patterns"
tags: [cheatsheet, ansible, automation]
---

# Ansible Cheatsheet


## Ad-hoc Commands

```bash
ansible all -m ping
ansible web -m shell -a "uptime"
ansible db -m yum -a "name=postgresql state=present" -b
ansible all -m copy -a "src=file dest=/tmp/file"
```

## Playbook

```bash
ansible-playbook playbook.yml
ansible-playbook playbook.yml --check  # Dry run
ansible-playbook playbook.yml --limit web
ansible-playbook playbook.yml --tags deploy
ansible-playbook playbook.yml -e "env=prod"
```

## Vault

```bash
ansible-vault create secrets.yml
ansible-vault edit secrets.yml
ansible-vault encrypt file.yml
ansible-playbook playbook.yml --ask-vault-pass
```
