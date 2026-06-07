# 🚀 Git & GitHub Complete Notes

A complete guide to Git and GitHub covering commands, branching strategies, pull requests, merge conflicts, stash, revert, reset, GitHub workflows, and interview questions.

---

# 📖 Table of Contents

1. What is Version Control?
2. Git vs GitHub
3. Git Architecture
4. Git Installation & Configuration
5. Repository Commands
6. Staging & Commit Commands
7. Push, Pull & Fetch
8. Branching Strategy
9. Pull Requests (PR)
10. Merge vs Rebase
11. Git Stash
12. Git Conflicts
13. Git Revert & Reset
14. Tags
15. .gitignore
16. Fork
17. SSH Authentication
18. GitHub Features
19. GitHub Actions
20. Real-Time Workflow
21. Interview Questions

---

# What is Version Control?

Version Control System (VCS) is used to track and manage source code changes over time.

### Benefits

- Tracks code history
- Supports team collaboration
- Allows rollback to previous versions
- Resolves merge conflicts
- Maintains audit trail

### Popular VCS

- Git
- GitHub
- BitBucket
- SVN

---

# Git vs GitHub

## Git

- Distributed Version Control System
- Installed locally
- Tracks source code changes

## GitHub

- Cloud-based repository hosting platform
- Used for collaboration and code sharing

### Interview Answer

Git is a version control system used to track code changes, whereas GitHub is a cloud platform used to host Git repositories and collaborate with teams.

---

# Git Architecture

```text
Working Tree
     ↓
Staging Area
     ↓
Local Repository
     ↓
Remote Repository (GitHub)
```

### Working Tree

Developer writes code here.

### Staging Area

Files ready for commit.

### Local Repository

Stores commits locally.

### Remote Repository

Stores code on GitHub.

---

# Git Installation

## Verify Installation

```bash
git --version
```

## Configure Username

```bash
git config --global user.name "Your Name"
```

## Configure Email

```bash
git config --global user.email "yourmail@gmail.com"
```

## Check Configuration

```bash
git config --list
```

---

# Repository Commands

## Initialize Repository

```bash
git init
```

## Clone Repository

```bash
git clone <repo-url>
```

## Clone Specific Branch

```bash
git clone -b <branch-name> <repo-url>
```

---

# Status Commands

## Check Status

```bash
git status
```

## Commit History

```bash
git log
```

## One-Line History

```bash
git log --oneline
```

---

# Staging Commands

## Add Single File

```bash
git add <file-name>
```

## Add All Files

```bash
git add .
```

---

# Restore Commands

## Remove From Staging

```bash
git restore --staged <file-name>
```

## Discard Local Changes

```bash
git restore <file-name>
```

---

# Commit Commands

## Commit Changes

```bash
git commit -m "commit message"
```

## Amend Last Commit

```bash
git commit --amend
```

---

# Push Commands

## Push Changes

```bash
git push
```

## Push Branch

```bash
git push origin develop
```

---

# Pull Commands

## Pull Latest Changes

```bash
git pull
```

## Pull Specific Branch

```bash
git pull origin develop
```

---

# Fetch Commands

## Fetch Changes

```bash
git fetch
```

## Fetch Specific Branch

```bash
git fetch origin develop
```

---

# Fetch vs Pull

## Git Fetch

```bash
git fetch
```

Downloads latest changes but does not merge them.

## Git Pull

```bash
git pull
```

Downloads and merges latest changes.

```text
git pull = git fetch + git merge
```

---

# Branch Commands

## View Branches

```bash
git branch
```

## Create Branch

```bash
git branch feature-login
```

## Switch Branch

```bash
git checkout feature-login
```

or

```bash
git switch feature-login
```

## Create & Switch Branch

```bash
git checkout -b feature-login
```

## Delete Branch

```bash
git branch -d feature-login
```

---

# Real-Time Branching Strategy

```text
main
│
develop
│
├── feature/login
├── feature/payment
├── feature/orders
│
sit
│
uat
│
release
│
hotfix
```

### Branch Purpose

| Branch | Purpose |
|----------|----------|
| main | Production |
| develop | Integration |
| feature | Development |
| sit | System Testing |
| uat | User Acceptance Testing |
| release | Release Preparation |
| hotfix | Production Fixes |

---

# Merge

## Merge Branch

```bash
git merge develop
```

## Abort Merge

```bash
git merge --abort
```

---

# Pull Request (PR)

Pull Request is a request to merge changes from one branch to another.

```text
feature/login
      ↓
Pull Request
      ↓
develop
```

### Benefits

- Code Review
- Collaboration
- Quality Checks

---

# Merge vs Rebase

## Merge

```bash
git merge feature-login
```

Creates merge commit.

## Rebase

```bash
git rebase develop
```

Creates linear history.

### Interview Answer

Merge preserves history, whereas rebase rewrites commit history to create a cleaner linear timeline.

---

# Git Stash

Used to temporarily store uncommitted changes.

## Save Changes

```bash
git stash
```

## View Stashes

```bash
git stash list
```

## Apply Stash

```bash
git stash apply
```

## Apply & Remove

```bash
git stash pop
```

## Delete Stash

```bash
git stash drop
```

---

# Git Conflicts

Occurs when multiple developers modify the same code section.

### Resolution Steps

1. Open conflicted file
2. Resolve conflict manually
3. Save file
4. Commit changes

---

# Remove Files

```bash
git rm <file-name>
```

Example:

```bash
git rm Employee.java
```

Then:

```bash
git commit -m "Removed file"
git push
```

---

# Git Revert

Safely undo a commit.

```bash
git revert <commit-id>
```

Creates a new commit that reverses changes.

---

# Git Reset

## Soft Reset

```bash
git reset --soft HEAD~1
```

## Mixed Reset

```bash
git reset HEAD~1
```

## Hard Reset

```bash
git reset --hard HEAD~1
```

---

# Revert vs Reset

| Revert | Reset |
|----------|----------|
| Safe | Risky |
| Creates New Commit | Removes Commit |
| Used in Shared Branches | Used Locally |

---

# Git Tags

## Create Tag

```bash
git tag v1.0
```

## List Tags

```bash
git tag
```

## Push Tag

```bash
git push origin v1.0
```

---

# .gitignore

Example:

```gitignore
target/
.idea/
.settings/
.classpath
*.log
.env
```

Used to ignore unnecessary files and folders.

---

# Fork

Fork creates a copy of another repository into your GitHub account.

Used heavily in open-source development.

---

# Remote Commands

## View Remote

```bash
git remote -v
```

## Add Remote

```bash
git remote add origin <repo-url>
```

## Remove Remote

```bash
git remote remove origin
```

---

# SSH Authentication

## Generate SSH Key

```bash
ssh-keygen -t rsa -b 4096
```

## View Public Key

```bash
cat ~/.ssh/id_rsa.pub
```

## Test GitHub Connection

```bash
ssh -T git@github.com
```

---

# GitHub Features

- Repositories
- Pull Requests
- Issues
- Discussions
- Wiki
- Projects
- Releases
- Security
- GitHub Actions

---

# GitHub Actions (CI/CD)

```text
Push Code
     ↓
GitHub Actions
     ↓
Build
     ↓
Test
     ↓
Deploy
```

Used for CI/CD automation.

---

# Real-Time Workflow

```text
Requirement
      ↓
JIRA Story
      ↓
Feature Branch Creation
      ↓
Development
      ↓
git add .
      ↓
git commit
      ↓
git push
      ↓
Pull Request
      ↓
Code Review
      ↓
Merge
      ↓
Build
      ↓
Deployment
```

---

# Frequently Asked Interview Questions

### What is Git?

A distributed version control system.

### What is GitHub?

A cloud platform for hosting Git repositories.

### What is Pull Request?

A request to merge code between branches.

### Difference Between Fetch and Pull?

Fetch downloads changes only, whereas pull downloads and merges changes.

### What is Git Stash?

Temporary storage for uncommitted changes.

### What is Git Conflict?

Occurs when Git cannot automatically merge changes.

### Difference Between Revert and Reset?

Revert creates a new commit; reset rewrites history.

### Difference Between Merge and Rebase?

Merge preserves history; rebase creates a linear history.

### What is .gitignore?

File used to exclude files from Git tracking.

### What is Fork?

A copy of another repository in your GitHub account.

### What is GitHub Actions?

GitHub's CI/CD automation service.

---

⭐ If these notes helped you, consider giving the repository a star.
