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

## 📥 2. Creating Tags
➤ Tagging the Latest Commit
```
git tag v2.0.0
```
➤ Tagging a Specific Commit
```
git tag v2.0.0 <commit-hash>
```

Example:
```
git tag v2.0.0 a3f5e9d
```
➤ Create Annotated Tag
```
git tag -a v2.1.0 -m "Added authentication system"
```

## 📄 3. Listing Tags

➤ List all tags
```
git tag
```
➤ Search tags matching a pattern
```
git tag -l "v2.*"
```

## ✏️ 4. Viewing Tag Details

➤ Show info about an annotated tag:
```
git show <tag-name>

```
Example:
```
git show v1.0.0
```

## 🔄 5. Sharing Tags with Remote

➤ Push a single tag
```
git push origin <tag-name>
```
➤ Push all local tags
```
git push origin --tags
```

## ❌ 6. Deleting Tags

➤ Delete a local tag
```
git tag -d <tag-name>
```

Example:

git tag -d v1.0.0

➤ Delete a remote tag
```
git push origin --delete <tag-name>
```

Example:
```
git push origin --delete v1.0.0
```

## 📝 7. Updating (Moving) a Tag

Tags normally should not move, but it is technically possible.

➤ Move a tag to a different commit:
```
git tag -f <tag-name> <commit-hash>
```

Example:
```
git tag -f v1.0.0 HEAD~1
```
➤ Force-push the updated tag
```
git push origin -f <tag-name>
```

⚠️ Warning: Moving tags can break other people's builds.

## 📦 8. Creating Release Versions (Semantic Versioning)

Common convention:
```
v<major>.<minor>.<patch>
```

Examples:
```
v1.0.0 — first stable release

v1.1.0 — added new features

v1.1.1 — bug fixes
```
Tags make releases easy and trackable.

## 📚 9. Common Use Cases

✔ Marking production releases
```
git tag -a v1.0.0 -m "Production build"
```
✔ Marking sprint milestones
```
git tag sprint-5-end
```
✔ Marking major code refactors
```
git tag refactor-frontend
```
✔ Marking hotfix commits
```
git tag hotfix-login-bug
```

## 💡 10. Best Practices

- Prefer annotated tags over lightweight tags.

- Use semantic versioning (v1.2.3) for clarity.

- Always push tags after creating important releases.

- Never move or delete tags unless absolutely necessary.

- Tag meaningful events, not random commits.

