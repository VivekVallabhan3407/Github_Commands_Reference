# 🌉 Git Merging Guide

This page contains essential Git commands and explanations for merging branches, resolving merge conflicts, understanding fast-forward vs non-fast-forward merges, and safely combining changes.
Each section includes clear examples and recommended practices.

## 🚀 1. Basics of Merging
### 1.1 Merge a Branch Into the Current Branch
```
git merge <branch-name>
```
Combines the specified branch into the branch you are currently on.

Example: merging feature-login into main.

Before merging, always ensure your working directory is clean.

### 1.2 Fast-Forward Merge

Occurs when your current branch has no new commits compared to the target branch.

git merge <branch-name>


Git simply moves the pointer forward, no new commit is created.

✔ Clean and simple
✔ No merge commit
✔ Happens when branches have no divergence

### 1.3 Non-Fast-Forward Merge (Default)

If both branches have diverged, Git creates a merge commit.

git merge <branch-name>


A merge commit with two parents is created to combine histories.

✔ Keeps full history
✔ Easier to understand long-term changes

## 🔧 2. Controlling Merge Behavior
### 2.1 Force a Merge Commit (Disable Fast-Forward)
git merge --no-ff <branch-name>


Creates a merge commit even if a fast-forward merge is possible.

Useful for:
✔ Tracking feature branch history
✔ Clean PR structure
✔ Team workflows

### 2.2 Merge with a Custom Commit Message
git merge -m "Your message here" <branch-name>


Allows you to specify a message for the merge commit.

### 2.3 Abort an In-Progress Merge
git merge --abort


Stops the merge and resets the working tree to the pre-merge state.

Use when:
⚠️ Conflicts are too complex
⚠️ You merged accidentally

## ⚠️ 3. Merge Conflicts
### 3.1 When Conflict Happens

You’ll see messages like:

CONFLICT (content): Merge conflict in <file>
Automatic merge failed; fix conflicts and then commit the result.


Git cannot automatically combine changes.

3### .2 Identifying Conflict Sections

Git marks conflicting lines like:

<<<<<<< HEAD
your changes
=======
incoming branch changes
>>>>>>> feature-branch


You must edit the file and keep/remove/merge code manually.

### 3.3 After Resolving the Conflict
git add <file>
git commit


Git finalizes the merge.

## 🧹 4. Cleaning Up After Merge
### 4.1 Remove the Merged Branch
git branch -d <branch-name>


Deletes the branch only if it is fully merged.

### 4.2 Force Delete Even If Not Merged
git branch -D <branch-name>


⚠️ DANGEROUS — deletes unmerged work permanently.

## 🔄 5. Merging vs Rebasing (Brief Compare)
5### .1 Merge

Keeps full branch history

Creates merge commits

Easier for teams

Good for shared branches

### 5.2 Rebase

Linear, clean history

No merge commits

Better for personal branches

⚠️ Should not rebase public/shared branches

## 📝 6. Example Merge Workflow (Simple)
# Step 1 — switch to the branch you want to merge into
git switch main

# Step 2 — merge feature branch
git merge feature-login

# Step 3 — delete merged branch
git branch -d feature-login

# Step 4 — push updated main
git push origin main
