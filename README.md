# Getting Started with Git and GitHub/new_feature(branch)

Welcome! This guide is for beginners who want to set up and start using Git and GitHub efficiently.

---

![Build Status](https://img.shields.io/badge/build-passing-brightgreen)
![License](https://img.shields.io/badge/license-MIT-blue)

## Table of Contents

- [Getting Started with Git and GitHub/new_feature(branch)](#getting-started-with-git-and-githubnew_featurebranch)
  - [Table of Contents](#table-of-contents)
  - [1. Setting Up Your Git Credentials](#1-setting-up-your-git-credentials)
  - [2. Generating and Adding an SSH Key to GitHub](#2-generating-and-adding-an-ssh-key-to-github)
  - [3. Creating a New Repository on GitHub](#3-creating-a-new-repository-on-github)
  - [4. Cloning an Existing Repository](#4-cloning-an-existing-repository)
  - [5. Basic Git Workflow](#5-basic-git-workflow)
  - [6. Common Git Commands](#6-common-git-commands)
  - [7. Resolving Merge Conflicts](#7-resolving-merge-conflicts)
  - [8. Why Use Git and GitHub?](#8-why-use-git-and-github)
  - [9. Visualizing Git Workflows](#9-visualizing-git-workflows)
  - [10. Pull Requests for Collaboration](#10-pull-requests-for-collaboration)
    - [How to Create a Pull Request:](#how-to-create-a-pull-request)
  - [11. Troubleshooting Common Issues](#11-troubleshooting-common-issues)
  - [12. Git Cheat Sheet](#12-git-cheat-sheet)

---

## 1. Setting Up Your Git Credentials

Before you start using Git, configure your credentials to identify yourself in commits.

1. **Set your GitHub username:**

   ```bash
   git config --global user.name "YourGitHubUsername"
   ```

2. **Set your GitHub email (must match the email used for your GitHub account):**

   ```bash
   git config --global user.email "your@email.com"
   ```

3. **Ensure your default branch name is `main` (important for new repositories):**

   ```bash
   git config --global init.defaultBranch main
   ```

4. **Verify your configuration:**

   ```bash
   git config --list
   ```

   Sample output:

   ```bash
   user.name=YourGitHubUsername
   user.email=your@email.com
   init.defaultBranch=main
   ```

---

## 2. Generating and Adding an SSH Key to GitHub

Using SSH for authentication makes your workflow more secure and convenient.

1. **Generate an SSH key:**

   ```bash
   ssh-keygen -t ed25519 -C "your@email.com"
   ```

   - When prompted, press `Enter` to accept the default location.
   - Leave the passphrase empty for easier access.

2. **Display your SSH public key:**

   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```

3. **Add the SSH key to your GitHub account:**

   - Go to [GitHub SSH settings](https://github.com/settings/keys).
   - Click **"New SSH key"**.
   - Paste your key and give it a meaningful title.
   - Click **"Add SSH key"**.

   ![New SSH Key Button](sshbutton.png)
   ![Add SSH Key](newsshsubmit.png)

4. **Test your SSH connection:**

   ```bash
   ssh -T git@github.com
   ```

   If successful, you'll see a message like:

   ```bash
   Hi username! You've successfully authenticated, but GitHub does not provide shell access.
   ```

---

## 3. Creating a New Repository on GitHub

1. **Create a repository on GitHub:**

   - Go to [GitHub](https://github.com) and click **"New Repository"**.
   - Choose a name, description, and visibility (public/private).
   - Click **"Create repository"**.

2. **Initialize a Git repository locally:**

   ```bash
   git init
   ```

3. **Add a remote repository:**

   ```bash
   git remote add origin git@github.com:yourusername/your-repo-name.git
   ```

4. **Add and commit files:**

   ```bash
   git add .
   git commit -m "Initial commit"
   ```

5. **Push changes to GitHub:**

   ```bash
   git push -u origin main
   ```

---

## 4. Cloning an Existing Repository

If you want to work on an existing project, clone it to your local machine:

```bash
   git clone git@github.com:username/repository-name.git
```

Navigate to the project directory:

```bash
   cd repository-name
```

---

## 5. Basic Git Workflow

1. **Check the status of your repository:**

   ```bash
   git status
   ```

2. **Stage your changes:**

   ```bash
   git add .
   ```

3. **Commit the changes with a message:**

   ```bash
   git commit -m "Updated feature"
   ```

4. **Push your changes to GitHub:**

   ```bash
   git push
   ```

---

## 6. Common Git Commands

Here are some common Git commands you might find useful:

- **Check the current branch:**

  ```bash
  git branch
  ```

- **Create a new branch:**

  ```bash
  git checkout -b new-branch-name
  ```

- **Switch to an existing branch:**

  ```bash
  git checkout branch-name
  ```

- **Merge a branch into the current branch:**

  ```bash
  git merge branch-name
  ```

- **Delete a branch:**

  ```bash
  git branch -d branch-name
  ```

---

## 7. Resolving Merge Conflicts

Merge conflicts occur when changes from different branches conflict with each other. Here's how to resolve them:

1. **Identify the files with conflicts:**

   ```bash
   git status
   ```

2. **Open the conflicted files and manually resolve the conflicts. Look for conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`) and edit the file to resolve the conflicts.**

3. **After resolving the conflicts, stage the resolved files:**

   ```bash
   git add resolved-file
   ```

4. **Commit the resolved changes:**

   ```bash
   git commit -m "Resolved merge conflicts"
   ```

---

## 8. Why Use Git and GitHub?

Git and GitHub are essential tools for managing and collaborating on projects. Here are some common use cases:

- **Collaborative Coding**: Work together on the same codebase while tracking who made which changes.
- **Open-Source Contributions**: Contribute to projects like React, Linux, or TensorFlow.
- **Backup and Version Control**: Safeguard your code and revisit previous versions when needed.
- **Portfolio Building**: Showcase your projects to potential employers by hosting them on GitHub.

---

## 9. Visualizing Git Workflows

A simple branching workflow:

```plaintext
main
 |
 |-------- feature-branch
 |                 |
 |                 |------- Bug fix
 |                 |               |
 |                 |               |----- Merge into main
```

Branches allow you to isolate features, bug fixes, or experiments from the main codebase, avoiding conflicts.

---

## 10. Pull Requests for Collaboration

Pull requests (PRs) are how developers suggest changes in a shared repository. They are great for:

- Discussing changes with collaborators.
- Reviewing code to ensure quality and consistency.
- Merging changes into the main branch after approval.

### How to Create a Pull Request:

1. Push your branch to GitHub:

   ```bash
   git push origin your-branch-name
   ```

2. Go to your repository on GitHub.
3. Click **Pull Requests** > **New Pull Request**.
4. Select the branch to merge and submit your request!

---

## 11. Troubleshooting Common Issues

**1. SSH Key Issues**

- Problem: `Permission denied (publickey)` when trying to push.
- Solution:
  - Ensure your SSH key is added to GitHub ([steps here](https://github.com/settings/keys)).
  - Check if the SSH agent is running:
    ```bash
    eval "$(ssh-agent -s)"
    ssh-add ~/.ssh/id_ed25519
    ```

**2. Conflicts During Merge**

- Problem: Git shows a merge conflict after pulling changes.
- Solution:
  - Use `git status` to identify conflicted files.
  - Open the conflicted files, manually resolve the conflict, then:
    ```bash
    git add resolved-file
    git commit -m "Resolved conflicts"
    ```

---

## 12. Git Cheat Sheet

```plaintext
# Basic Git Commands
git init                 # Initialize a new repository
git clone <url>          # Clone a repository
git branch               # List branches
git checkout -b <name>   # Create and switch to a new branch
git add .                # Stage changes
git commit -m "<msg>"    # Commit changes
git push origin <branch> # Push branch to remote
git pull                 # Pull latest changes
```

---

Congratulations! You've successfully set up your GitHub credentials, created an SSH key, and pushed your first project to GitHub. Happy coding! 🚀
