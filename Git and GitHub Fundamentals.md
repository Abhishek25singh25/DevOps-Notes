# Git Fundamentals

Git is a distributed version control system used to track changes in source code.

It allows multiple developers to collaborate efficiently and maintain code history.

In DevOps, Git is essential because CI/CD pipelines and automation workflows depend on version control.

---

## What is Version Control?

Version control is a system that records changes to files over time.

Benefits:

- Track code history
- Revert to previous versions
- Collaborate with teams
- Manage multiple features

---

## What is Git?

Git is:

- Distributed
- Fast
- Reliable
- Widely used in software development

Each developer has a full copy of the repository.

---

## Git Basic Workflow

1. Modify files
2. Stage changes
3. Commit changes
4. Push to remote repository

Commands:

git init  
git add .  
git commit -m "message"  
git push  

---

## Important Concepts

### Repository
A project tracked by Git.

### Commit
A snapshot of changes at a specific time.

### Branch
A separate line of development.

### HEAD
Pointer to the current branch.

---

## Checking Repository Status

git status – Shows current state  
git log – Shows commit history  
git diff – Shows differences  

---

## Branching Basics

Create branch:

git branch branch-name  

Switch branch:

git checkout branch-name  

Create and switch:

git checkout -b branch-name  

Merge branch:

git merge branch-name  

Branching allows working on features without affecting main code.

---

## Remote Repositories

Remote repositories are hosted on platforms like GitHub.

Add remote:

git remote add origin repository-url  

Push changes:

git push origin main  

Pull changes:

git pull origin main  

---

## .gitignore

Used to ignore files that should not be tracked.

Example:

node_modules/  
.env  

Important for security and clean repositories.

---

## Why Git is Important in DevOps

- CI/CD pipelines trigger on Git commits
- Infrastructure as Code stored in Git
- Collaboration across teams
- Rollback capabilities

Strong Git fundamentals are required for modern DevOps workflows.
