# 📄 About this page:

This page contains the most essential Git commands for starting a repository, checking status, staging changes, committing, and basic inspection.
Each command is numbered, shown with a code block, and includes a simple explanation.

## 🚀 1. Initialize a Repository
### 1.1 git init

```
git init

```

Creates a new empty Git repository in the current folder.
It initializes a .git directory that tracks your project history.

## 📥 2. Clone a Repository
### 2.1 git clone <url>

```
git clone https://github.com/user/repo.git

```

Downloads a copy of an existing repository to your machine.


## 🔍 3. Check the Status

### 3.1 git status

```
git status

```

Shows:

    - Modified files

    - Untracked files

    - Staged files

    - Current branch

Great for knowing what’s going on before a commit.


## ➕ 4. Add (Stage) Files

### 4.1 Add a single file
```
git add file.txt
```

Stages ONLY that file.

### 4.2 Add everything
```
git add .
```

Stages all modified and new files.

### 4.3 Add an entire folder
```
git add src/
```

Useful when making changes inside a specific directory.

## 📝 5. Commit Changes

### 5.1 Normal commit
```
git commit -m "Meaningful message"
```

Saves the staged changes into Git history with short normal message.

### 5.2 Commit with extended description
```
git commit -m "Title line" -m "Extended detailed explanation."
```

Saves the staged changes into Git history by giving commit wiht title line and extended detailed explaination.

## 🛑 6. See Commit History
### 6.1 Basic log
```
git log
```

Shows a list of all commits with IDs, messages, and authors.

### 6.2 One-line cleaner view
```
git log --oneline

```
Useful for quick review.



## 🗑️ 7. Remove Files
### 7.1 Remove a tracked file
```
git rm file.txt
```
Remove a file from tracking.

### 7.2 Remove from Git but keep locally
```
git rm --cached file.txt
```

Used when you mistakenly tracked a file (like .env).


## 📂 8. View Differences

### 8.1 Check unstaged changes
```
git diff
```
Check the changes that are unstaged(those that git has seen) but not added using git add command to your git repository.


### 8.2 Check staged changes
```
git diff --staged
```

Check the changes that are staged or added to git and are ready to be commited to your git repository.
