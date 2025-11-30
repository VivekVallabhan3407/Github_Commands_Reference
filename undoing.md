# ♻️ Undoing Changes in Git

This page explains the essential Git commands for undoing mistakes — including unstaging changes, reverting commits, resetting versions, discarding local edits, and fixing the last commit.
Each section includes the command, usage example, and a clear explanation.

## 🔄 1. Unstage Files (Move from Staged → Unstaged)

### 1.1 Unstage a Single File
```
git restore --staged <file>
```

Removes the file from the staging area while keeping the working directory changes.

### 1.2 Unstage All Files
```
git restore --staged .
```

Moves every staged file back to the unstaged area.

## 📝 2. Discard Working Directory Changes

### 2.1 Discard Changes in a File
```
git restore <file>
```

Reverts the file to the last committed state.
⚠️ Cannot be undone.

### 2.2 Discard All Local Changes
```
git restore .
```

Resets all tracked files in the working directory to their last commit.

## ♻️ 3. Revert a Commit (Safe, Public History)

### 3.1 Revert a Specific Commit
```
git revert <commit-hash>
```

Creates a new commit that undoes the changes of a previous commit.
Used for shared/public branches.

### 3.2 Revert a Range of Commits
```
git revert <old-commit>..<new-commit>
```

Reverts multiple commits one by one.

## 🧹 4. Resetting Commits (Dangerous – Rewrites History)

### 4.1 Soft Reset (Keep all changes staged)
```
git reset --soft <commit-hash>
```

Moves HEAD to the given commit.
Your changes stay in the staging area.

### 4.2 Mixed Reset (Default)
```
git reset <commit-hash>
```

Moves HEAD and unstages everything.
Your working directory stays untouched.

### 4.3 Hard Reset (⚠️ Most Dangerous)
```
git reset --hard <commit-hash>
```

Resets everything (HEAD, staging, working directory) to the target commit.
All local changes are lost permanently.

## ✏️ 5. Fixing the Last Commit

### 5.1 Modify Last Commit Message
```
git commit --amend
```

Reopens the last commit to edit its message.

### 5.2 Add More Changes to the Last Commit
```
git add <file>
git commit --amend
```

Stages new changes and adds them to the most recent commit.

## 🕵️ 6. View History Before Undoing

### 6.1 See Commit Log (One Line)
```
git log --oneline
```

Useful for identifying the commit hash before resetting or reverting.

### 6.2 See Detailed Commit History
```
git log
```

Shows full commit messages, authors, and timestamps.

## ❗ 7. Undo Local File Deletion

### 7.1 Restore a Deleted File (Before Commit)
```
git restore <file>
```

Brings the file back from the last committed version.

## ❗ 8. Undo a Merge (If Not Pushed)

### 8.1 Cancel a Merge in Progress
```
git merge --abort
```

Stops an ongoing merge and restores the pre-merge state.