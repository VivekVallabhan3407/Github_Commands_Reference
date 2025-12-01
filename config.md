# ⚙️ Git Configuration Guide

This page covers all essential Git configuration commands — setting your identity, viewing configs, managing global vs. local settings, changing default editors, creating aliases, and configuring line endings.
Each command includes clear explanations and examples.


## 🧑‍💻 1. User Identity Configuration

### 1.1 Set Global Username
```
git config --global user.name "<your-name>"
```

Sets the username for all repositories on your system.

### 1.2 Set Global Email
```
git config --global user.email "<your-email>"
```

GitHub requires an email for commit attribution.

### 1.3 Set Username for a Single Repository
```
git config user.name "<your-name>"
```

### 1.4 Set Email for a Single Repository
```
git config user.email "<your-email>"
```

Stored in .git/config of that repo only.


## 📋 2. Viewing Configuration

### 2.1 View All Global Settings
```
git config --global --list
```
### 2.2 View All Local Settings (Repo Only)
```
git config --local --list
```
### 2.3 View All System Settings
```
git config --system --list
```
### 2.4 View a Specific Setting
```
git config <key>
```

Example:
```
git config user.name
```

## 📝 3. Editor Configuration

### 3.1 Set VS Code as Default Editor
```
git config --global core.editor "code --wait"
```
### 3.2 Set Vim as Editor
```
git config --global core.editor "vim"
```
### 3.3 Set Notepad++ on Windows
```
git config --global core.editor "'C:/Program Files/Notepad++/notepad++.exe' -multiInst -nosession"
```

## 📌 4. Default Branch Configuration

### 4.1 Set Default Branch Name
```
git config --global init.defaultBranch main
```

Newly initialized repos will start with main.

## 🎨 5. Color & Output Formatting

### 5.1 Enable Colored Output
```
git config --global color.ui auto
```

### 5.2 Disable Colored Output
```
git config --global color.ui false
```


## 🚀 6. Aliases (Shortcuts)

### 6.1 Show All Aliases
```
git config --global --list
```

Aliases appear as alias.<name>=...

Popular aliases:
### 6.2 git st → status
```
git config --global alias.st "status"
```
### 6.3 git co → checkout
```
git config --global alias.co "checkout"
```
### 6.4 git br → branch list
```
git config --global alias.br "branch"
```
### 6.5 git lg → pretty log graph
```
git config --global alias.lg "log --oneline --graph --decorate --all"
```
### 6.6 git cm → commit with message
```
git config --global alias.cm "commit -m"
```

## 🔀 7. Merge & Diff Configuration

### 7.1 Set Merge Tool
```
git config --global merge.tool <tool-name>
```
### 7.2 Set Diff Tool
```
git config --global diff.tool <tool-name>
```
### 7.3 Example (VS Code as merge tool)
```
git config --global merge.tool vscode
git config --global mergetool.vscode.cmd "code --wait $MERGED"
```
### 7.4 Run the Merge Tool
```
git mergetool
```
### 7.5 Run the Diff Tool
```
git difftool
```


## 📂 8. Line Ending Settings (Windows/macOS/Linux)

### 8.1 Normalize Line Endings (recommended for all systems)
```
git config --global core.autocrlf true
```
### 8.2 Only Warn About Incorrect Line Endings
```
git config --global core.safecrlf warn
```
### 8.3 Convert LF → CRLF Automatically (Windows)
```
git config --global core.autocrlf true
```
### 8.4 Keep LF Always (Linux/Mac)
```
git config --global core.autocrlf input
```

## 🔐 9. Credential Storage


9.1 Store Credentials Locally
```
git config --global credential.helper store
```

9.2 Cache Credentials Temporarily
```
git config --global credential.helper cache
```

Default timeout is 15 minutes.


9.3 Set Custom Cache Timeout (e.g., 2 hours)
```
git config --global credential.helper "cache --timeout=7200"
```