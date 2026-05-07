# Production-Grade Git Branching Strategy

A clean and scalable Git workflow for:
- Solo developers
- Small teams
- DevOps projects
- CI/CD pipelines
- Kubernetes projects
- Documentation/MkDocs projects
- Production-grade repositories

---

# 1. Recommended Branch Structure

```text
main
 └── production-ready code only

dev
 └── active integration branch

feature/*
 └── temporary feature branches
```

Example:

```text
main
dev
feature/docker-setup
feature/github-actions
feature/k8s-monitoring
```

---

# 2. Recommended Workflow Strategy

| Branch | Purpose | Merge Strategy |
|---|---|---|
| feature → dev | Development integration | Squash Merge |
| dev → main | Production release | Squash Merge |
| main | Production only | Protected |

---

# 3. Initial Repository Setup

## Step 1 — Create Local Repository

```bash
mkdir my-project
cd my-project

git init
```

---

## Step 2 — Create Initial Files

```bash
touch README.md
```

---

## Step 3 — Initial Commit

```bash
git add .
git commit -m "chore: initial commit"
```

---

## Step 4 — Create Repository on GitHub

Create a new repository on GitHub.

Recommended:
- DO NOT initialize README
- DO NOT initialize .gitignore
- DO NOT initialize license

---

## Step 5 — Connect Local Repository to GitHub

```bash
git remote add origin https://github.com/username/my-project.git
```

Verify:

```bash
git remote -v
```

---

## Step 6 — Rename Default Branch to main

```bash
git branch -M main
```

---

## Step 7 — Push main Branch

```bash
git push -u origin main
```

---

# 4. Create Permanent dev Branch

## Create dev Branch

```bash
git checkout -b dev
```

---

## Push dev Branch

```bash
git push -u origin dev
```

Now:
- `main` → production-ready
- `dev` → active development

---

# 5. Starting New Feature Development

Always create feature branches from `dev`.

---

## Pull Latest Changes

```bash
git checkout dev
git pull origin dev
```

---

## Create Feature Branch

```bash
git checkout -b feature/docker-setup
```

Examples:

```text
feature/auth-system
feature/mkdocs-search
feature/github-actions
feature/k8s-dashboard
```

---

## Push Feature Branch

```bash
git push -u origin feature/docker-setup
```

---

# 6. Local Development Workflow

## Recommended Development Flow

```text
feature branch
    ↓
local development
    ↓
local testing
    ↓
push to GitHub
    ↓
PR to dev
    ↓
squash merge
```

---

## Check Git Status

```bash
git status
```

---

## Add Changes

```bash
git add .
```

---

## Commit Changes

Good examples:

```bash
git commit -m "feat: add docker compose setup"
git commit -m "fix: correct nginx configuration"
git commit -m "docs: update installation guide"
```

Bad examples:

```bash
git commit -m "changes"
git commit -m "update"
```

---

# 7. Recommended Commit Message Convention

Use Conventional Commits.

## Common Types

```text
feat:
fix:
docs:
refactor:
test:
ci:
chore:
style:
```

---

## Examples

```bash
git commit -m "feat: add prometheus monitoring"
git commit -m "fix: resolve kubectl namespace issue"
git commit -m "docs: update README"
git commit -m "ci: add GitHub Actions workflow"
```

---

# 8. Keep Feature Branch Updated with dev

Before creating PR:

```bash
git checkout dev
git pull origin dev

git checkout feature/docker-setup
git rebase dev
```

---

## Push Rebased Branch

```bash
git push --force-with-lease
```

---

# 9. Testing Before Merge

Before merging:
- Run unit tests
- Run lint checks
- Run Docker builds
- Validate CI/CD
- Verify deployments
- Test locally

Examples:

```bash
docker compose up

pytest

npm test

mkdocs serve
```

---

# 10. Pull Request Strategy

## Goals

- Clean Git history
- One clean commit in production
- No unnecessary development commits
- Easier rollback
- Easier auditing

---

# 11. Merge Strategies Explained

## A. Merge Commit (Not Recommended)

```text
main
 ├── commit1
 ├── commit2
 ├── merge commit
```

Problems:
- Noisy history
- Harder to track releases
- Many unnecessary commits

---

## B. Rebase Merge

Keeps history linear but preserves all commits.

Useful for:
- Advanced teams
- Detailed history tracking

Not ideal for your requirement.

---

## C. Squash Merge (Recommended)

```text
feature branch commits:
- commit 1
- commit 2
- commit 3

↓

main:
- ONE CLEAN COMMIT
```

Benefits:
- Clean history
- Easy rollback
- Better release management
- Professional Git history

---

# 12. Recommended Merge Flow

## Feature → dev

```text
feature/docker-setup
    →
dev
```

Use:
✅ Squash Merge

Result:
- only one commit enters `dev`

---

## Testing on dev

Validate:
- CI/CD pipelines
- Docker builds
- Integration testing
- Kubernetes deployment
- Staging environment

---

## dev → main

```text
dev
 →
main
```

Again:
✅ Squash Merge

Result:
- production remains clean

---

# 13. Final Clean History Example

```text
main
 ├── feat: add docker monitoring stack
 ├── feat: add github actions workflow
 ├── feat: add kubernetes deployment
 ├── fix: resolve production nginx issue
```

---

# 14. Branch Cleanup

## Delete Local Feature Branch

```bash
git branch -d feature/docker-setup
```

Force delete:

```bash
git branch -D feature/docker-setup
```

---

## Delete Remote Feature Branch

```bash
git push origin --delete feature/docker-setup
```

---

# Important

DO NOT delete:
- `main`
- `dev`

Delete only:
- `feature/*`
- `hotfix/*`

---

# 15. GitHub Branch Protection Settings

Go to:

```text
GitHub Repository
→ Settings
→ Branches
```

---

# Protect main Branch

Enable:
- Require pull request before merge
- Require approvals
- Require status checks
- Block force pushes
- Block branch deletion

---

# Protect dev Branch

Recommended:
- Require pull request
- Optional CI checks

---

# 16. Enable Squash Merge Only

Go to:

```text
Settings
→ General
→ Pull Requests
```

Enable:
- ✅ Allow squash merging

Disable:
- ❌ Merge commits
- ❌ Rebase merging

---

# 17. Disable Direct Pushes to main

Branch Protection Rule:

```text
Require pull request before merging
```

This prevents accidental production commits.

---

# 18. Recommended CI/CD Checks

Examples:
- lint validation
- unit tests
- docker build validation
- security scans
- terraform validate
- markdown linting

---

# Example GitHub Actions Workflow

```yaml
name: CI

on:
  pull_request:

jobs:
  test:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4

      - name: Run Tests
        run: echo "Testing..."
```

---

# 19. Hotfix Workflow

Production issue?

Create hotfix branch from `main`.

---

## Create Hotfix Branch

```bash
git checkout main
git pull origin main

git checkout -b hotfix/login-fix
```

---

## After Fix

Merge:
- hotfix → main
- hotfix → dev

Then delete hotfix branch.

---

# 20. Release Tagging

## Create Release Tag

```bash
git tag -a v1.0.0 -m "Release v1.0.0"
```

---

## Push Tag

```bash
git push origin v1.0.0
```

---

# 21. Semantic Versioning

Format:

```text
MAJOR.MINOR.PATCH
```

Example:

```text
1.0.0
```

| Version Type | Meaning |
|---|---|
| Major | Breaking changes |
| Minor | New features |
| Patch | Bug fixes |

---

# 22. Useful Git Aliases

## Configure Aliases

```bash
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.cm commit
git config --global alias.lg "log --oneline --graph --all"
```

---

## Usage

```bash
git st
git co dev
git lg
```

---

# 23. Recommended .gitignore

```gitignore
.env
node_modules/
__pycache__/
*.pyc
.terraform/
.vscode/
.idea/
dist/
build/
coverage/
```

Useful generator:

https://www.toptal.com/developers/gitignore

---

# 24. Complete Real-World Example

# Start New Feature

```bash
git checkout dev
git pull origin dev

git checkout -b feature/github-actions
```

---

# Make Changes

```bash
git add .
git commit -m "feat: add github actions workflow"

git add .
git commit -m "fix: correct docker build step"
```

---

# Push Feature Branch

```bash
git push -u origin feature/github-actions
```

---

# Update Feature Branch with Latest dev

```bash
git checkout dev
git pull origin dev

git checkout feature/github-actions
git rebase dev
```

---

# Open Pull Request

```text
feature/github-actions
    →
dev
```

Use:
✅ Squash Merge

---

# Delete Feature Branch

```bash
git branch -d feature/github-actions

git push origin --delete feature/github-actions
```

---

# Release to main

```text
dev
 →
main
```

Again:
✅ Squash Merge

---

# 25. Common Mistakes to Avoid

## Bad Practice

❌ Direct commits to `main`

---

## Bad Practice

❌ Large untested commits

---

## Bad Practice

❌ Long-lived feature branches

---

## Bad Practice

❌ Force push on shared branches

---

## Bad Practice

❌ Mixing unrelated changes

---

## Bad Practice

❌ Skipping code reviews

---

# 26. Final Recommended Production Workflow

```text
main
 └── production only

dev
 └── active integration

feature/*
 └── temporary branches
```

---

# Final Development Flow

```text
feature/*
   ↓
dev
   ↓
main
```

---

# Recommended Merge Type

✅ Squash Merge Everywhere

---

# Benefits of This Workflow

- Clean Git history
- Easier rollback
- Better production stability
- Professional workflow
- CI/CD friendly
- Easier code reviews
- Better collaboration
- Scalable structure
- Cleaner releases