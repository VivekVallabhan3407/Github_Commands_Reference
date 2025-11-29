# 📦 Git Stash Guide

This page contains the essential Git commands for stashing your changes — temporarily saving work without committing, applying stashes, managing multiple stashes, and dropping or clearing them.
Useful when you need to switch branches quickly without losing uncommitted changes.

## 🚀 1. Basic Stashing
### 1.1 Create a Stash
```
git stash
```

Temporarily saves all tracked file changes and cleans your working directory.

### 1.2 Stash With a Message
```
git stash push -m "<message>"
```

Creates a stash with a custom label for easier identification.

### 1.3 Stash Untracked Files Too
```
git stash -u
```

Includes untracked files in the stash.
```
git stash -a
```

Includes all files, including ignored ones (use carefully).

## 👀 2. Viewing Stashes
### 2.1 List All Stashes
```
git stash list
```

Shows all saved stashes with index numbers.

### 2.2 Show Changes Inside a Stash
```
git stash show
```

Shows a summary of changes.
```
git stash show -p
```

Shows the full patch (detailed diff).

## 🎯 3. Applying & Pop Stash
### 3.1 Apply the Most Recent Stash
```
git stash apply
```

Applies the stash but keeps it in the stash list.

### 3.2 Apply a Specific Stash
```
git stash apply stash@{2}
```

Applies the stash with the given index.

### 3.3 Pop (Apply + Remove)
```
git stash pop
```

Applies the latest stash and removes it afterward.
```
git stash pop stash@{1}

```
Pop a specific stash.

## 🗑️ 4. Removing Stashes
### 4.1 Drop a Single Stash
```
git stash drop stash@{0}
```

Deletes one stash entry.

### 4.2 Clear All Stashes
```
git stash clear
```

Removes all stash entries permanently.

## 🧪 5. Advanced Stashing
### 5.1 Stash Only Specific Files
```
git stash push <file1> <file2>
```

Stashes selected files instead of the entire working directory.

### 5.2 Create a Branch From a Stash
```
git stash branch <branch-name>
```

Creates a new branch and applies the stash onto it directly.

Useful when a stash becomes significant work.

### 5.3 Save Stash Without Cleaning Working Directory
```
git stash push --keep-index
```

Stashes only unstaged changes and keeps staged ones intact.