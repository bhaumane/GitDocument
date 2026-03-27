# Git & GitHub – Advanced Guide for Developers

## 📌 Introduction

**Git**:
Git is a Version Control System. It is: Popular, Free & Open Source, Fast & Scalable.
Version control System is a tool that helps to track changes in code.
  
**GitHub**:
Website that allows developers to store and manage their code using Git
https://github.com

---

## Setting up Git

    - Visual Studio Code
    - Windows (Git Bash)
    - Mac (Terminal)

---

**Command to check git installed or not**
```bash
git --version
```

## ⚙️ Configuring Git

```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
git config --list   # To view what is configured
```

**Credential.helper** : store user credentials (e.g user name, email etc)

---

## Clone & Status

**Clone**: cloning a repository on our local machine
```bash
git clone < github repository link >
```

**Status**: display the state of the code
```bash
git status
```
- **untracked**: new files that git doesn’t yet track
- **modified**: changed
- **staged**: file is ready to be committed
- **unmodified**: unchanged

---

## Add & Commit:
**add**: adds new or changed files in your working directory to the Git staging area.
```bash
	git add < file name >
	git add .	#To add all the files
```
**commit**: it is the record of change
```bash
	git commit -m “commit message”
```

---

## Push command:
**push**: upload local repositories content to remote repositories
```bash
	git push origin main
```

---

## Init command:
**Init**: used to create a new git repository
```bash
git init
git remote add origin < github repository link >
git remote -v 		# to verify remote
git branch 		# to check branch
git branch -M main	# to rename branch
git push origin main / git push -u origin main
git remote remove origin # To remove origin
```

---


## 🔄 File Lifecycle

```
Untracked → Modified → Staged → Committed
```

```bash
git status
git add <file>
git add .
git commit -m "message"
```

---

## Git WorkFlow:
```
GitHub repo → Clone → Make changes → add in local repo → commit → push in GitHub repo
```
---

## Branch Commands
```bash
git branch	                # to check branch
git branch -M main          # to rename branch
git checkout <branch name> 	# to navigate branch or to switch to another branch 
git checkout -b <new branch name>	# to create new branch
git branch -d <branch name>	        # to delete branch
```
---

## Merging code:
**Way 1**:
```bash
	git diff <branch name>	# to compare commits, branches, files & more
	git merge <branch name>	# to merge 2 branches
```
**Way 2**:
Create Pull Request:
It lets you tell others about changes you’ve pushed to a branch in a repository on GitHub.

---

## Pull command:
Used to fetch and download content from a remote repository and immediately update the local repository to match the content.

```bash
git pull origin main
```
---

**Resolving Merge Conflicts**:
An event that takes place when Git is unable to automatically resolve differences in code between two commits.

---

## Upstream branch:
To push the current branch and set the remote as upstream, use
```bash
git push –set-upstream origin feature
```

---

## Undoing Changes:
**Case1**: staged changes
```bash
	git reset < file name >	# For single file
	git reset			      # For multiple files
```
**Case2**: committed changes (for one commit)
```bash
	git reset HEAD~1
```
**Case3**: committed changes (for many commit)
```bash
	git reset < commit hash >
	git reset --hard < commit hash >
```

---

## Fork:
A fork is a new repository that shares code and visibility settings with the original “upstream” repository.
Fork is a rough copy.

---



## 🧠 Git Architecture Overview

```
Working Directory → Staging Area → Local Repository → Remote Repository
```

### Explanation:
- **Working Directory**: Where files are edited
- **Staging Area**: Where changes are prepared
- **Local Repository**: Stores commits locally
- **Remote Repository**: Hosted on GitHub

---



## 📁 Repository Management

```bash
git init
git clone <repo-url>
git remote add origin <repo-url>
git remote -v
```

---



## 🌿 Branching Strategy

### Create & Switch

```bash
git branch
git checkout -b feature/login
git checkout main
```

### Rename & Delete

```bash
git branch -M main
git branch -d feature/login
```

---

## 🔀 Merging vs Rebase

### Merge

```bash
git merge feature/login
```

### Rebase

```bash
git rebase main
```

### Difference:

| Merge | Rebase |
|------|--------|
| Keeps history | Rewrites history |
| Safe for shared branches | Avoid on public branches |

---

## 🔗 Remote Operations

```bash
git push origin main
git pull origin main
git fetch origin
```

### Upstream

```bash
git push --set-upstream origin feature/login
```

---

## 🔥 Advanced Commands

### View Commit History

```bash
git log
git log --oneline --graph --all
```

### Show Changes

```bash
git diff
git diff HEAD~1
```

### Stashing

```bash
git stash
git stash pop
git stash list
```

---

## ⏪ Undo Changes

```bash
git reset <file>
git reset HEAD~1
git reset --hard <commit>
```

### Revert (Safe Undo)

```bash
git revert <commit>
```

---

## ⚔️ Merge Conflicts

```
<<<<<<< HEAD
Your changes
=======
Incoming changes
>>>>>>> branch
```

### Steps:
1. Edit file
2. Remove markers
3. Add & commit

---

## 🔁 Git Workflow Diagram

```
         ┌──────────────┐
         │   GitHub     │
         └──────┬───────┘
                │
            git clone
                │
        ┌───────▼────────┐
        │ Local Repo      │
        └───────┬────────┘
                │
         git add / commit
                │
            git push
                │
         ┌──────▼───────┐
         │   GitHub     │
         └──────────────┘
```

---

## 🔄 Pull Request Workflow

1. Create branch
2. Push branch
3. Open Pull Request
4. Code review
5. Merge

---

## 🍴 Forking Workflow

```
Original Repo → Fork → Clone → Changes → PR to Original Repo
```

---

## 🛠️ Best Practices

- Use meaningful commit messages
- Keep commits small
- Use feature branches
- Pull before push
- Use `.gitignore`

---

## ⚠️ Common Mistakes

- Using `--hard` reset carelessly
- Rebasing public branches
- Not resolving conflicts properly
- Committing large/binary files

---

## 📚 Useful Tips

```bash
ls -a
git help <command>
```

---
