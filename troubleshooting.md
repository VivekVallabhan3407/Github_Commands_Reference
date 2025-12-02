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

