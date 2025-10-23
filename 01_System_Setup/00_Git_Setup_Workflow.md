# Git Setup and Daily Workflow Essentials

This guide covers the basic commands for initializing a Git repository and maintaining the daily sync between local and remote repositories.

---

## 1. Initial Git Setup (Remote Repo - Local Repo)

### A. Starting a New Project

1.  **Create Local Folder & Initialize Git:**
    ```bash
    mkdir new-project
    cd new-project
    git init
    ```
2.  **Create Initial File & Commit:**
    ```bash
    echo "# New Project" > README.md
    git add .
    git commit -m "Initial commit"
    ```
3.  **Create Remote Repo (GitHub) & Connect:**
    ```bash
    # (Create repository on GitHub website first)
    git remote add origin [https://github.com/your-username/new-project.git](https://github.com/your-username/new-project.git)
    git push --set-upstream pidog-learning master
    ```

### B. Cloning an Existing Project

This single command handles folder creation, Git initialization, and setting up the `origin` remote.

```bash
git clone [https://github.com/jisunpark-ca/pidog-learning.git](https://github.com/jisunpark-ca/pidog-learning.git)
cd pidog-learning
# Start work.
```

### C. Re-establishing Remote Connection

If your local folder is already a Git repository but lost its remote connection:

1.  **Navigate to local folder:**
    ```bash
    cd pidog-learning
    ```
2.  **Add remote connection (use 'origin' as the standard name):**
    ```bash
    git remote add origin [https://github.com/jisunpark-ca/pidog-learning.git](https://github.com/jisunpark-ca/pidog-learning.git)
    ```
    *(Optional)* **Set Tracking Branch (if needed):**
    ```bash
    git push --set-upstream pidog-learning master
    ```
---

## 2. Daily Git Synchronization (Push & Pull)

| Action | Command | Description |
| :--- | :--- | :--- |
| **Get Latest Changes** | `git pull` | Fetches the latest remote changes and merges them into the local branch. (Most frequent sync command)|
| **Upload Local Work** | `git push` | Uploads locally committed changes to the remote repository. |

### Standard Workflow Sequence (Before/After Work)

1.  **Start Work:** Update local branch with remote changes.
    ```bash
    git pull
    ```
2.  **Perform Work:** Modify code, add files, etc.
3.  **Commit:** Stage changes and record locally.
    ```bash
    git add .
    git commit -m "Descriptive commit message"
    ```
3.  **Publish:** Upload local commits to the remote repository.
    ```bash
    git push
    ```

---
## 🚨 Nested Folder Structure (e.g., folder/folder)

This often occurs when using `git clone` into an existing, same-named directory.

### To fix the structure (moving contents up one level):

#### Move Contents Up: Move all contents from the inner folder to the current (outer) directory.
```bash
# Power Shell (Windows):
Move-Item .\pidog-learning\* .
```
#### Remove Empty Inner Folder:
```bash
# Power Shell (Windows):
Remove-Item .\pidog-learning -Recurse -Force
```

## 🚨 Common Push Error & Fix

If you see the error: `fatal: The current branch master has no upstream branch.`, use the following command to set the tracking relationship permanently:

```bash
git push --set-upstream pidog-learning master
```
---
