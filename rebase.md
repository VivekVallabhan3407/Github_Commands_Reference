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

