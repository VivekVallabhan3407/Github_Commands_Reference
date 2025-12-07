# 🔄 workflows.md
About this File

This file explains commonly used Git workflows — how developers organize branches, merge strategies, release cycles, and collaboration patterns.
It covers GitHub Flow, Git Flow, Trunk-Based Development, Forking Workflow, and real-world examples for each.

## 🔄 Git Workflows — Complete Guide

Different teams use different Git workflows depending on project size, release cycle, and collaboration style.
This guide explains the 4 most widely used workflows and how to use them effectively.

### 🚀 1. GitHub Flow (Modern, Simple)

A lightweight workflow used by GitHub and most modern SaaS teams.

✔ Ideal For:

- Continuous deployment (CD)

- Small-to-medium teams

- Web apps with frequent updates

🔧 How It Works

1. You start from the main branch.

2. Create a feature branch:

```
git switch -c feature/login-ui
```

3. Do work → commit → push:
```
git push -u origin feature/login-ui
```

4. Open a Pull Request on GitHub.

5. Team reviews the PR.

6. Merge into main using:

- Squash merge (clean history)

- Rebase + merge

- Merge commit (rare)

7. Deploy automatically from main.

⭐ Summary Diagram
```
main ← feature/login-ui ← PR → merge → deploy
```

## 🌳 2. Git Flow (Enterprise / Release-Based)

A more structured workflow with dedicated branches.

✔ Ideal For:

- Large teams

- Versioned releases (v1.0, v2.0)

- Long-running development cycles

🔧 Branch Types

- main → Production code

- develop → Integration branch

- feature/* → Feature development

- release/* → Pre-release stabilization

- hotfix/* → Quick production fixes

🔧 How It Works
✔ Start a feature
```
git switch develop
git switch -c feature/payment-integration
```
✔ Finish a feature (merge into develop)
```
git switch develop
git merge feature/payment-integration
```
✔ Start a release
```
git switch -c release/1.2.0 develop
```
✔ After testing, merge release into both:
```
git switch main
git merge release/1.2.0
```
git switch develop
git merge release/1.2.0
```
✔ Add a tag for production
```
git tag -a v1.2.0 -m "Release 1.2.0"
git push origin v1.2.0
```

## 🌿 3. Trunk-Based Development (Fastest Workflow)

Used by Google, Meta, and many high-speed engineering teams.

✔ Ideal For:

- High deployment frequency

- Very fast iteration

- Small, short-lived branches

🔧 How It Works

1. Always work from main (trunk).

2. Create tiny short-lived feature branches:
```
git switch -c fix-button-color
```

3. Finish work quickly (max 1–2 days).

4. Rebase onto latest main:
```
git fetch
git rebase origin/main
```

5. Merge back into main (squash merge).

⭐ Key Rules

- No long-lived branches.

- Minimal merge conflicts.

- Heavy use of feature flags.