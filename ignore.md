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