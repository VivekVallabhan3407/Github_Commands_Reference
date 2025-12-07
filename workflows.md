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