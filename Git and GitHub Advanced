# Git Advanced

Git Advanced concepts help manage complex workflows, collaboration, and history management.

These concepts are essential in real-world DevOps and production environments.

---

## Git Reset

Used to move HEAD to a previous commit.

Types:

--soft → Keeps changes staged  
--mixed → Keeps changes unstaged (default)  
--hard → Deletes changes completely  

Example:

git reset --hard HEAD~1

⚠ Warning: --hard is destructive.

---

## Git Revert

Creates a new commit that undoes changes from a previous commit.

Example:

git revert commit-id

Safe for shared branches because it does not rewrite history.

---

## Reset vs Revert

Reset:
- Rewrites history
- Can remove commits
- Not safe for shared branches

Revert:
- Creates new commit
- Preserves history
- Safe for shared repositories

---

## Git Rebase

Reapplies commits on top of another base branch.

Example:

git rebase main

Benefits:

- Cleaner history
- Linear commit structure

⚠ Be careful when rebasing shared branches.

---

## Git Stash

Temporarily saves uncommitted changes.

Save changes:

git stash

Apply stash:

git stash pop

Useful when switching branches quickly.

---

## Git Cherry-pick

Applies a specific commit from one branch to another.

git cherry-pick commit-id

Useful when you need one specific change.

---

## Git Reflog

Shows all actions performed in Git, including resets.

git reflog

Used to recover lost commits.

---

## Branching Strategies

### GitFlow
- develop branch
- feature branches
- release branches
- hotfix branches

### GitHub Flow
- main branch
- short-lived feature branches

### Trunk-Based Development
- Everyone commits to main
- Small frequent changes

---

## Why Git Advanced Matters in DevOps

- Managing large teams
- Handling production fixes
- Safe rollbacks
- Clean history management
- CI/CD stability

Advanced Git knowledge is critical for real production workflows.
