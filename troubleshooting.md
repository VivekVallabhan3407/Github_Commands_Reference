# 🛠️ Git Troubleshooting Guide

This page provides solutions for the most common Git errors — authentication issues, merge conflicts, detached HEAD state, permission problems, failed pushes, and more.
Each problem includes causes, fixes, and example commands

## 🔐 1. Authentication & Permission Errors
❌ Error: “Authentication failed”

Often happens when using HTTPS without token or using an expired token.

✅ Fix

Use a personal access token (PAT) instead of a password.

Update your saved credentials.
```
git config --global credential.helper store
```

To re-enter token, run any Git command like:
```
git pull
```

❌ Error: “Permission denied (publickey)”

Happens when using SSH without proper key setup.

✅ Fix

### 1. Generate SSH key:
```
ssh-keygen -t ed25519 -C "your-email@example.com"
```

### 2. Start SSH agent:
```
eval "$(ssh-agent -s)"
```

### 3. Add key:
```
ssh-add ~/.ssh/id_ed25519
```

### 4. Add the public key to GitHub.

## 🔄 2. Pull / Push Errors

❌ Error: “failed to push some refs”

You are behind the remote branch.

✅ Fix (safe way)
```
git pull --rebase origin main
git push
```
⚠️ OR force push (dangerous)
```
git push --force
```

❌ Error: “Updates were rejected because the remote contains work…”

Means remote has commits you don't have.

✅ Fix
```
git pull --rebase
```
❌ Error: “non-fast-forward”

Your history diverged.

✅ Fix

Pull and rebase:
```
git pull --rebase origin main
```


## 🔀 3. Merge Conflict Troubleshooting

❌ Problem: Merge conflict detected

Git cannot auto-merge two branches.

🔍 See conflicting files:
```
git status
```
🛠️ Fix conflicts manually:

Edit files → remove conflict markers:

<<<<<<< HEAD
your changes
=======
their changes
>>>>>>> branch

Mark resolved:
```
git add <file>
git commit
```
❌ You merged wrongly & want to undo it

If merge is not pushed:
```
git merge --abort
```

If merge is committed but not pushed:
```
git reset --hard HEAD~1
```

## 🎯 4. Detached HEAD Issues

❌ You're in “detached HEAD” state

This happens after checking out a commit instead of a branch.

🔧 Fix: Switch back to a branch
```
git switch main
```
Save your work as a proper branch:
```
git switch -c new-branch-name
```

## ♻️ 5. Undoing Mistakes

❌ Undo last commit (keep changes)
```
git reset --soft HEAD~1
```
❌ Undo last commit (discard changes)
```
git reset --hard HEAD~1

```
❌ Undo staged file
```
git restore --staged <file>
```
❌ Undo unstaged file
```
git restore <file>
```

## 📦 6. Stash Problems
❌ Error: “Your local changes would be overwritten by checkout”

Fix: stash your changes.
```
git stash
git switch <branch>
```
❌ Want to apply stash but keep it
```
git stash apply
```
❌ Want to apply and remove the stash
```
git stash pop
```

## 🔍 7. Diagnosing Repository Issues
❓ See what branch you are on:
```
git branch
```
❓ Show changed files:
```
git status
```
❓ Show log with details:
```
git log --oneline --graph --decorate --all
```
❓ See differences:
```
git diff
```
❓ Check remote URL:
```
git remote -v
```

