# 🌿 Git Branching & Merging Guide

This page contains the essential Git commands for working with branches — creating, switching, listing, renaming, merging, deleting, and resolving common workflow tasks.
Each command includes a short explanation and usage example.

## 🚀 1. Working With Branches
1.1 Create a New Branch
```
git branch <branch-name>
```

Creates a new branch from the current HEAD.
Does not switch you to it.

### 1.2 Switch to a Branch
```
git switch <branch-name>
```

Moves the working directory to the specified branch.

### 1.3 Create & Switch (Shortcut)
```
git switch -c <branch-name>
```

Creates a new branch and switches to it immediately.


### 1.4 List Branches
```
git branch
```

Shows all local branches. The branch with * is the active branch.


### 1.5 List Remote Branches
```
git branch -r
```

Displays branches that exist only on the remote (e.g., origin).

### 1.6 List All (Local + Remote)
```
git branch -a
```

Shows local and remote branches together.



## ✏️ 2. Renaming Branches

### 2.1 Rename Current Branch
```
git branch -m <new-name>
```

Renames the branch you are currently on.

### 2.2 Rename Another Branch
```
git branch -m <old-name> <new-name>
```

Renames a branch that is not currently checked out.


## 🗑️ 3. Deleting Branches

### 3.1 Delete a Local Branch
```
git branch -d <branch-name>
```

Deletes the branch only if it is fully merged.

### 3.2 Force Delete a Local Branch
```
git branch -D <branch-name>
```

Forcibly deletes the branch even if not merged.
⚠️ Use with caution — irreversible.

### 3.3 Delete Remote Branch
```
git push origin --delete <branch-name>
```

Removes the branch from the remote repository.


## 🔀 4. Merging Branches
4.1 Merge a Branch Into Current Branch

```
git merge <branch-name>
```

Merges the specified branch into your currently active branch.

Example:
If you're on main and run git merge feature-1, it merges feature-1 into main.

4.2 Abort a Merge

```
git merge --abort
```

Cancels the merge process and restores your working directory to the previous state.

## 🎯 5. Inspecting Branch Differences
5.1 See Differences Between Two Branches

```
git diff <branch-A> <branch-B>
```

Shows what changed between the two branches before merging.

5.2 See Commits Not Merged Yet

```
git log <branch-name> --oneline
```

OR

```
git log <branch-A>..<branch-B> --oneline
```

Shows commits that are unique to each branch.

## 📤 6. Pushing & Tracking Branches
6.1 Push a New Branch to Remote

```
git push -u origin <branch-name>
```

Uploads your local branch and sets upstream tracking so future pushes only require:
```
git push
```

6.2 Push Changes to an Existing Remote Branch

```
git push
```

Pushes commits to its upstream branch (set earlier using -u).

## 📥 7. Pulling & Updating Branches
7.1 Pull Latest Changes

```
git pull
```

Fetches and merges the latest remote changes into your current branch.

7.2 Update Local Branch List

```
git fetch
```

Downloads new branch info without merging anything.

## 🧹 8. Cleaning Up Branches
8.1 View Branches Merged Into Current Branch

```
git branch --merged
```

Shows branches safe to delete.

8.2 View Branches Not Merged
```
git branch --no-merged
```

Branches that still have unmerged changes.



