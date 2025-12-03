# 🌱 Git Rebase Guide

This page explains how to use Git Rebase — one of the most powerful tools for keeping your commit history clean and linear.
It covers basic rebasing, interactive rebasing, fixing commits, squashing, rewording, and handling conflicts.

## 🚀 1. What is Rebase?

Rebasing moves or replays commits from one branch onto another.
It creates a clean, linear history (unlike merge, which creates merge commits).

Simple definition:

Rebase = rewriting commit history by applying your commits on top of another branch.

## 📌 2. Basic Rebase
2.1 Rebase Current Branch onto Another Branch
git rebase <base-branch>


Example:
```
git rebase main
```

This takes your current branch’s commits and reapplies them on top of main.

2.2 Rebase a Specific Branch
```
git rebase <base-branch> <topic-branch>
```

Example:
```
git rebase main feature/login
```

Rebases feature/login onto main.

## 🧹 3. Updating Feature Branches

### 3.1 Bring Feature Branch Up-to-Date with Main
```
git checkout feature
git fetch origin
git rebase origin/main
```

This keeps history clean instead of merging main into your feature branch.

## ✏️ 4. Interactive Rebase (Editing History)

- Interactive rebase lets you:

- Reorder commits

- Edit commit messages

- Squash multiple commits

- Delete commits

4.1 Start Interactive Rebase
```
git rebase -i HEAD~<n>
```

Example: Rewrite the last 5 commits
```
git rebase -i HEAD~5
```

This opens a list of commits with options like:
- pick
- reword
- edit
- squash
- fixup
- drop

## ✂️ 5. Squashing Commits

Combine multiple commits into one.

### 5.1 Squash Last Two Commits (Interactive)
```
git rebase -i HEAD~2
```

Change:

pick abc123 First commit
pick def456 Second commit


To:

pick abc123 First commit
squash def456 Second commit


Save → Git combines the commits.

## 📝 6. Editing Commit Messages

### 6.1 Reword the Last Commit (Without Rebase)
```
git commit --amend
```
### 6.2 Reword Older Commits
```
git rebase -i HEAD~<n>
```

Set the desired commit to:

reword

## 🔧 7. Editing Commit Content

### 7.1 Edit an Older Commit
```
git rebase -i HEAD~<n>
```

Change the commit to:

edit


Git stops at that commit → you modify files → stage changes → continue:

```
git add .
git rebase --continue
```

## 🗑 8. Dropping Commits

To delete a commit from history:
```
git rebase -i HEAD~<n>
```

Change:

pick abc123 commit message


To:

drop abc123 commit message