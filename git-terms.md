
# About this page:

# Git Terms & Workflow

This document explains the most commonly used Git terms in simple language.  
It also includes the basic Git workflow that shows how changes move from your computer to GitHub.

---

## 🔤 Common Git Terms

### 1. **Repository (Repo)**
A folder or project tracked by Git. It contains all files and the full version history.

### 2. **Working Directory**
Your actual project files on your computer where you make edits.

### 3. **Staging Area (Index)**
A holding area where Git keeps files that are ready to be committed.

### 4. **Commit**
A saved version of your project. Like taking a snapshot of your code.

### 5. **Branch**
A separate line of development. Lets you work on new features without affecting main code.

### 6. **Merge**
Combines changes from one branch into another.

### 7. **Remote**
A version of your repository stored online (e.g., GitHub).

### 8. **Origin**
The default name Git gives to your main remote repository on GitHub.

### 9. **Main / Master**
The primary branch of the repository. Newer repos use `main`.

### 10. **HEAD**
A pointer to your current branch or commit.

### 11. **Clone**
Download a remote repository to your computer.

### 12. **Pull**
Fetch changes from the remote and merge them into your local branch.

### 13. **Push**
Upload your local commits to the remote repository (GitHub).

### 14. **Conflict**
When Git cannot automatically merge changes from different places and needs your input.

---

## 🚩 Common Git Status Flags

When you run `git status` or `git diff --name-status`, Git shows short flags:

### 1. **M — Modified**
File has been changed but not yet staged (or is staged after modification).

### 2. **A — Added**
File is newly added to the staging area (`git add <file>`).

### 3. **D — Deleted**
File is deleted.

### 4. **R — Renamed**
File has been renamed.

### 5. **C — Copied**
Git detected a file copy.

### 6. **U — Unmerged / Conflict**
File has merge conflicts that must be resolved manually.

### 7. **?? — Untracked**
A new file that Git is not tracking yet.

### 8. **!! — Ignored**
File is ignored (listed in `.gitignore`).

---

## 🔄 Git Workflow (Simple Diagram)

```
    Working Directory (Edited Files)
            ↓ git add
    Staging Area (Ready to Commit)
            ↓ git commit
    Local Repository (Committed History)
            ↓ git push
    Remote Repository (GitHub)


```

---

## 📝 Workflow Explanation

1. You **edit files** in the Working Directory.  
2. You use **`git add`** to move selected changes into the Staging Area.  
3. You use **`git commit`** to save those staged changes into the Local Repository.  
4. You use **`git push`** to upload your commits to the Remote Repository (GitHub).

This is the basic flow used in almost every Git project.

---
