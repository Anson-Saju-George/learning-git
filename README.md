This cheat sheet covers the basic and essential Git commands that will help you navigate, manage, and push changes in your repository. Feel free to refer back to it as you practice Git. It provides both common use cases and solutions for handling files, commits, branches, and remote repositories.

---

# Git Command Cheat Sheet

## **1. Basic Commands for Navigating Directories**

- **Change Directory**:
  - `cd <path>` – Change to a specific directory.
    ```bash
    cd /path/to/directory
    ```

- **Go Up One Directory**:
  - `cd ..` – Navigate to the parent directory.
    ```bash
    cd ..
    ```

- **View Files in Directory**:
  - `ls` (Linux/macOS) / `dir` (Windows) – List the files in the current directory.
    ```bash
    ls    # Linux/macOS
    dir   # Windows
    ```

- **View Hidden Files** (Windows PowerShell):
  - `dir /a:h` – Display hidden files in the directory.
    ```bash
    dir /a:h
    ```

## **2. Creating and Initializing a Git Repository**

- **Create a New Directory**:
  - `mkdir <dir_name>` – Create a new directory.
    ```bash
    mkdir new_repo
    cd new_repo
    ```

- **Initialize a Git Repository**:
  - `git init` – Initialize a new Git repository in the current directory.
    ```bash
    git init
    ```

## **3. Viewing the Status of Your Repository**

- **Check the Current Status of the Repository**:
  - `git status` – Show the status of the files in the current Git repository.
    ```bash
    git status
    ```

    **Possible statuses**:
    - `Untracked files`: Files that are not yet tracked by Git.
    - `Changes to be committed`: Files staged to be committed.
    - `Changes not staged for commit`: Files that have been modified but not staged.

- **View the Commit Log**:
  - `git log` – Show the commit history.
    ```bash
    git log
    ```

  - `git log --oneline` – Display a simplified, one-line per commit view.
    ```bash
    git log --oneline
    ```

## **4. Managing Files in Git**

### **Adding Files**

- **Add a Single File**:
  - `git add <file_name>` – Add a specific file to the staging area.
    ```bash
    git add filename.txt
    ```

- **Add All Files in Directory**:
  - `git add .` – Add all new and modified files in the current directory and subdirectories.
    ```bash
    git add .
    ```

- **Add Specific Folder**:
  - `git add <folder_name>/` – Add all files in a specific folder to the staging area.
    ```bash
    git add my_folder/
    ```

- **Add Multiple Specific Files**:
  - `git add <file1> <file2> <file3>` – Add multiple specific files.
    ```bash
    git add file1.txt file2.py file3.md
    ```

- **Force Add a File (if ignored)**:
  - `git add -f <file_name>` – Force add a file that is ignored by `.gitignore`.
    ```bash
    git add -f ignored_file.txt
    ```

### **Committing Changes**

- **Commit Changes**:
  - `git commit -m "Commit message"` – Commit staged changes with a message.
    ```bash
    git commit -m "Initial commit"
    ```

- **Commit All Files (Staged + Unstaged)**:
  - `git commit -am "Commit message"` – This combines `git add` and `git commit` for modified files.
    ```bash
    git commit -am "Updated files"
    ```

### **Removing Files from Staging**

- **Unstage a File**:
  - `git reset <file_name>` – Remove a file from the staging area (without deleting it).
    ```bash
    git reset filename.txt
    ```

- **Unstage All Files**:
  - `git reset` – Unstage all files but keep them in the working directory.
    ```bash
    git reset
    ```

- **Remove File from Git (Delete File and Staging)**:
  - `git rm <file_name>` – Remove a file from the repository and the staging area.
    ```bash
    git rm unwanted_file.txt
    ```

### **Viewing Changes**

- **View Changes in Staged Files**:
  - `git diff --staged` – Show changes that are staged for the next commit.
    ```bash
    git diff --staged
    ```

- **View Changes in Unstaged Files**:
  - `git diff` – Show changes that are not staged yet.
    ```bash
    git diff
    ```

## **5. Pushing and Pulling Changes to/from a Remote Repository**

- **Add Remote Repository**:
  - `git remote add origin <repository_url>` – Link the local repo to a remote one.
    ```bash
    git remote add origin https://github.com/username/repository.git
    ```

- **Push to Remote Repository**:
  - `git push origin <branch_name>` – Push changes to the remote repository.
    ```bash
    git push origin master  # or main
    ```

- **Pull from Remote Repository**:
  - `git pull origin <branch_name>` – Pull the latest changes from the remote repository.
    ```bash
    git pull origin master
    ```

## **6. Deleting Files and Reverting Changes**

### **Delete Files Locally and Remotely**

- **Delete a Local File**:
  - `git rm <file_name>` – Delete a file from both the repository and your local directory.
    ```bash
    git rm unwanted_file.txt
    ```

- **Delete a Remote File**:
  - `git rm <file_name>` followed by `git commit` and `git push` to remove a file remotely.
    ```bash
    git rm unwanted_file.txt
    git commit -m "Deleted unwanted file"
    git push origin master
    ```

### **Undo Last Commit (Without Losing Changes)**

- **Undo the Last Commit but Keep Changes**:
  - `git reset --soft HEAD~1` – Remove the last commit but keep changes in the staging area.
    ```bash
    git reset --soft HEAD~1
    ```

- **Undo the Last Commit and Changes (Discard Changes)**:
  - `git reset --hard HEAD~1` – Remove the last commit and all changes.
    ```bash
    git reset --hard HEAD~1
    ```

### **Delete Git Repository (and Files)**

- **Delete the Git Repository**:
  - `rm -rf .git` (Linux/macOS) / `rmdir /s /q .git` (Windows) – Delete the `.git` folder to remove version control from the repository.
    ```bash
    rm -rf .git
    ```

- **Delete Remote Origin**:
  - `git remote remove origin` – Remove the connection to the remote repository.
    ```bash
    git remote remove origin
    ```

### **Reverting to a Previous Commit**

- **Revert a Specific Commit**:
  - `git revert <commit_id>` – Revert changes from a specific commit.
    ```bash
    git revert a1b2c3d
    ```

## **7. Branching and Merging**

- **Create a New Branch**:
  - `git branch <branch_name>` – Create a new branch.
    ```bash
    git branch feature-branch
    ```

- **Switch to a Different Branch**:
  - `git checkout <branch_name>` – Switch to an existing branch.
    ```bash
    git checkout feature-branch
    ```

- **Create and Switch to a New Branch**:
  - `git checkout -b <branch_name>` – Create a new branch and switch to it.
    ```bash
    git checkout -b new-feature
    ```

- **Merge a Branch into the Current Branch**:
  - `git merge <branch_name>` – Merge another branch into the current branch.
    ```bash
    git merge feature-branch
    ```

- **Delete a Branch**:
  - `git branch -d <branch_name>` – Delete a local branch after merging.
    ```bash
    git branch -d feature-branch
    ```

---
