---
title: "Git Cheatsheet"
description: "Essential Git commands for daily development"
tags: [cheatsheet, git, version-control]
---

# Git Cheatsheet


## Basics

```bash
git init
git clone url
git status
git add .
git commit -m "message"
git push origin branch
git pull origin branch
```

## Branching

```bash
git branch feature/name
git checkout -b feature/name
git merge feature/name
git branch -d feature/name
git rebase main
```

## Advanced

```bash
# Interactive rebase
git rebase -i HEAD~3

# Cherry-pick
git cherry-pick commit-hash

# Stash
git stash
git stash pop
git stash list

# Reset
git reset --soft HEAD~1   # Keep changes staged
git reset --hard HEAD~1   # Discard changes

# Bisect
git bisect start
git bisect bad
git bisect good commit-hash
```
