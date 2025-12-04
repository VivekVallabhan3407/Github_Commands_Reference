# Cherry-pick.md

About this File

This file explains Git cherry-pick, a powerful command used to copy specific commits from one branch to another. You will learn what it is, when to use it, how to avoid common mistakes, and advanced techniques for cleaner workflows. Includes all essential commands.

## 🍒 Git Cherry-Pick — Complete Guide
### 🔥 1. What is Cherry-Picking?

Cherry-picking means selecting one or more specific commits from any branch and applying them on top of your current branch — without merging the whole branch.

✅ Use Cases

- Apply a bug fix from one branch to another without merging the whole branch.

- Move selected commits from a messy experimental branch to a clean main branch.

- Apply a commit to many branches (hotfixes).

## 📌 2. Basic Cherry-Pick Usage

➤ Cherry-pick a single commit
```
git cherry-pick <commit-hash>
```
Example
```
git cherry-pick a3f52c1
```

## 📌 3. Cherry-Pick Multiple Commits

➤ Pick several commits individually
```
git cherry-pick <hash1> <hash2> <hash3>
```
➤ Pick a continuous range of commits
(From A to B, including both)
```
git cherry-pick A^..B

```
or
```
git cherry-pick A..B
```


(Some prefer A^..B for clarity because it includes A.)

## 📌 4. Cherry-Pick With Conflicts

If conflicts occur:

Step 1 — Fix conflicts
# open files, resolve conflicts manually

Step 2 — Mark files as resolved
```
git add .
```
Step 3 — Continue cherry-pick
```
git cherry-pick --continue
```
Abort if things get messy
```
git cherry-pick --abort
```

## 📌 5. Common Options
➤ --no-commit / -n

Apply changes without creating a commit.
```
git cherry-pick -n <hash>
```

Useful to combine multiple commits into one final commit.

➤ --edit

Open editor to modify commit message:
```
git cherry-pick --edit <hash>
```
➤ --signoff

Adds “Signed-off-by” line automatically.
```
git cherry-pick -s <hash>
```
➤ --strategy=<strategy>

Specify merge strategy during cherry-pick.
Example:
```
git cherry-pick -X ours <hash>
```

## 📌 6. Cherry-Pick in Detached HEAD

If you cherry-pick while not on any branch:
```
git checkout <branch>
git cherry-pick <hash>

```
or use temporary branch:
```
git switch -c temp
git cherry-pick <hash>
```
## 📌 7. Cherry-Pick from Another Branch
Example

Bring commit from feature/ui into main:
```
git switch main
git cherry-pick <commit-hash-from-feature-ui>
```
## 📌 8. Undo a Cherry-Pick

(If it was the most recent commit)
```
git reset --hard HEAD~1
```

If already pushed, use:
```
git revert <commit-hash>
```

## 📌 9. Best Practices & Warnings
✔ Good Use Cases

- Single commit bug fixes

- Selective patching

- Pulling useful work from unstable branches

✖ Avoid Cherry-Picking When

- The commit depends on previous commits

- There are many related commits — use merge or rebase instead

- It will cause duplication of history

⚠ Warning

Cherry-picking duplicates commit hashes → may cause confusion in large teams.