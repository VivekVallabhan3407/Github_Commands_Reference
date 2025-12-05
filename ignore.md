# Ignore.md

About this File

This file explains how Git ignores files and directories using .gitignore. It covers patterns, rules, global ignore configurations, common examples, troubleshooting, and best practices. This is a complete reference to help you understand and manage ignored files in any Git project.

🚫 Git Ignore — Complete Guide
## 🔥 1. What is .gitignore?

.gitignore is a special file that tells Git which files or folders should not be tracked.

You use it to ignore:

- Temporary files
- Build/output folders
- Environment files with secrets
- OS-specific junk files
- Log files

Any file pattern added in .gitignore will be skipped by Git unless already tracked.

## 📁 2. Creating a .gitignore File

Create it in the root of your repo:
```
touch .gitignore
```

Then add patterns inside it to ignore specific files.

## 🎯 3. Basic Ignore Rules

➤ Ignore a single file:
```
secret.txt
```
➤ Ignore a directory:
```
node_modules/
dist/
build/
```
➤ Ignore all files with an extension:
```
*.log
*.tmp
*.env
```
➤ Ignore all files in all folders:
```
*.DS_Store
*.class
```
➤ Ignore everything except something:
```
*.txt
!important.txt
```
➤ Ignore files in a specific folder only:
```
logs/*.log
```
➤ Ignore all files starting with a pattern:
```
temp*
debug*
```

## 🔍 4. Advanced Ignore Patterns

➤ Ignore using wildcard in the middle:
```
*config*
```
➤ Ignore root-only file:
```
/config.json
```
➤ Ignore folder but not its subfolder:
```
docs/*
!docs/important/
```
➤ Ignore everything in folder but allow one file:
```
assets/*
!assets/logo.png
```

## 📌 5. Commenting Inside .gitignore

You can add comments for clarity:
```
# Logs
*.log

# Node modules
node_modules/
```

## 🧹 6. Stop Tracking a File Already Tracked

.gitignore does NOT remove files already tracked.

To stop tracking a file:
```
git rm --cached <file>
```

Example:
```
git rm --cached .env
```

Then commit:
```
git commit -m "Stop tracking .env"
```

## 🌍 7. Global Git Ignore

You can set a global ignore file for all repos on your system.

➤ Step 1 — Create file:
```
touch ~/.gitignore_global
```
➤ Step 2 — Add rules inside it

(Example)
```
*.log
.DS_Store
Thumbs.db
```
➤ Step 3 — Configure Git to use it:
```
git config --global core.excludesfile ~/.gitignore_global
```

## 📚 8. Common .gitignore Examples
➤ Node.js
```
node_modules/
dist/
.env
*.log
```
➤ Python
```
__pycache__/
*.pyc
.env
```
➤ React / Vite
```
node_modules/
dist/
.env.local
```
➤ Java
```
*.class
target/
```
➤ Linux/Mac/Windows
```
.DS_Store
Thumbs.db
```

## ❗ 9. Troubleshooting Ignore Issues
✔ File still showing even after adding to .gitignore?

It’s probably already tracked.

Fix:
```
git rm --cached <file>
```
✔ .gitignore not working for nested folders?

Ensure correct pattern:

Bad:
```
logs
```

Good:
```
logs/
```
✔ Checking which .gitignore rule applies to a file
```
git check-ignore -v <file>
```

Example:
```
git check-ignore -v node_modules/
```


## ⭐ 10. Best Practices

- Always ignore sensitive files (.env, API keys)

- Ignore build artifacts (dist, build/)

- Use a global ignore file for OS junk files

- Never ignore source code accidentally

- Keep .gitignore clean and organized with comments