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


