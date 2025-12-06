# tags.md

About this File

This file explains everything about Git tags — what they are, why they are used, how to create, list, delete, push, and manage them. It includes lightweight and annotated tags, versioning conventions, and common workflows used in real projects.

🏷️ Git Tags — Complete Guide

Git tags are used to mark important points in history, usually releases such as v1.0, v2.1, etc.
Tags are not meant to move (unlike branches). They act like permanent labels.

## ⭐ 1. Types of Git Tags
### ✔️ 1.1 Lightweight Tag

A simple name pointing directly to a commit.
```
git tag <tag-name>
```

Example:
```
git tag v1.0.0
```

### ✔️ 1.2 Annotated Tag

Contains metadata — message, tagger name, email, and date.
```
git tag -a <tag-name> -m "Tag message"

```
Example:
```
git tag -a v1.0.0 -m "Initial release"
```

Annotated tags are preferred for releases.