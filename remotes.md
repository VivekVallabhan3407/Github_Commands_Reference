# 🌐 Git Remotes Guide

This page covers all essential Git commands related to working with remote repositories — adding, viewing, fetching, pulling, pushing, removing, and renaming remotes.
It includes practical explanations and safe workflows for syncing your local work with GitHub or any remote server.

## 🚀 1. Remote Basics
### 1.1 View Existing Remotes
```
git remote -v
```

Shows the list of remotes and their fetch/push URLs.

### 1.2 Add a Remote
```
git remote add origin <remote-url>
```

Adds a new remote.
Common default remote name is origin.

### 1.3 Remove a Remote
```
git remote remove <name>
```

Deletes a remote entry from your project (does NOT delete remote repo itself).

### 1.4 Rename a Remote
```
git remote rename <old-name> <new-name>
```

Renames a remote.
Useful when switching from origin → upstream or similar.

## 🔄 2. Syncing With Remotes
### 2.1 Fetch Changes (Safe)
```
git fetch origin
```

Downloads new commits/branches from remote without modifying your working directory.

### 2.2 Pull Changes (Fetch + Merge)
```
git pull
```

Fetches and automatically merges changes from the remote into your current branch.

To pull from a specific remote + branch:

git pull origin <branch-name>

### 2.3 Push Changes to Remote
```
git push origin <branch-name>
```

Uploads your commits to the specified remote branch.

First-time push (set upstream branch):

git push -u origin <branch-name>


After this, you can use:

git push


without arguments.

## 📦 3. Working With Remote Branches
### 3.1 List Remote Branches
```
git branch -r
```

Shows branches that exist on the remote but not necessarily locally.

### 3.2 Track a Remote Branch Locally
```
git checkout -b <local-branch> origin/<remote-branch>
```

Creates a local branch that tracks a remote branch.

### 3.3 Delete a Remote Branch
```
git push origin --delete <branch-name>
```

Removes a branch from the remote repository (safe and common cleanup practice).

## 🔁 4. Upstream & Tracking

### 4.1 Set Upstream Manually
```
git branch -u origin/<branch-name>
```

Links your current local branch to a remote branch.

### 4.2 View Upstream Branch
```
git branch -vv
```

Shows which local branch is tracking which remote branch.

## 🧠 5. Useful Remote Workflows
### 5.1 Clone a Remote Repo
```
git clone <remote-url>
```

Creates a full local copy of a remote repository.

### 5.2 Change Remote URL
```
git remote set-url origin <new-url>
```

Used when switching from HTTPS → SSH, or moving repos.

### 5.3 Fetch All Remotes
```
git fetch --all
```

Downloads updates from every configured remote.