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