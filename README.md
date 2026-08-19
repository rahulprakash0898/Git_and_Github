# Git and GitHub Cheatsheet

## Setup

| Command | Meaning |
|---------|---------|
| `git --version` | Check if Git is installed and see the installed version |
| `git config --global user.name "Name"` | Set your name (used to stamp every commit you make) |
| `git config --global user.email "email"` | Set your email (must match your GitHub account email) |
| `git config --list` | View all current Git settings |

---

## Basic Commands

| Command | Meaning |
|---------|---------|
| `git init` | Initialize a new Git repository in the current folder (start tracking a folder) |
| `git status` | Check which files have changed, which are staged, and which are untracked |
| `git add .` | Stage all changed files at once |
| `git commit -m "message"` | Save a permanent snapshot of all staged files with a description |
| `git log` | View the full detailed commit history |
| `git log --oneline` | View a compact one-line version of the commit history |
| `git log --oneline --graph --all` | View commit history as a visual branch graph |
| `git diff` | See the actual lines that were added or removed in your files |

---

## Undoing Changes

| Command | Meaning |
|---------|---------|
| `git restore --staged .` | Unstage ALL files |
| `git restore .` | Discard ALL changes in the Working Directory |
| `git reset --soft HEAD~1` | Undo the last commit, but keep the changes in the Staging Area |
| `git reset HEAD~1` | Undo the last commit and unstage the changes (Mixed Reset) |
| `git reset --hard HEAD~1` | Undo the last commit and permanently DELETE all changes (Hard Reset) |
| `git reset <commit-id>` | Go back to a specific commit in the history |
| `git revert <commit-id>` | Safely undo a commit by creating a NEW commit that reverses it (safe for pushed code) |

---

## Branching

| Command | Meaning |
|---------|---------|
| `git branch` | List all local branches (the `*` shows your current branch) |
| `git branch name` | Create a new branch |
| `git branch -M main` | Rename the current branch to `main` (commonly used after `git init` when default branch is `master`) |
| `git checkout name` | Switch to an existing branch |
| `git checkout -b name` | Create a new branch AND switch to it in one command |
| `git branch -d name` | Delete a branch (safe — only works if the branch has been merged) |
| `git branch -D name` | Force delete a branch even if it has not been merged |

---

## Merging

| Command | Meaning |
|---------|---------|
| `git merge feature` | Merge a feature branch into the current branch (Fast-Forward if possible) |
| `git merge feature -m "msg"` | Three-Way Merge — merges with a custom commit message (avoids Vim editor) |
| `git merge --squash feature` | Squash all commits from the feature branch into one staged change (you must commit manually after) |
| `git merge branch-1 branch-2 branch-3 -m "msg"` | Octopus Merge — merge multiple independent branches at once |
| `git merge --abort` | Cancel an in-progress merge and go back to the state before the merge |



---

## GitHub — Remote Repository

| Command | Meaning |
|---------|---------|
| `git clone <url>` | Download a complete copy of a repository from GitHub to your computer |
| `git remote add origin <url>` | Connect your local repository to a GitHub remote URL (nicknamed "origin") |
| `git remote -v` | View all configured remote connections and their URLs |
| `git push -u origin main` | Push local commits to GitHub for the first time and set the upstream tracking |
| `git push` | Push committed changes to GitHub (after the first push) |
| `git pull` | Download and merge the latest changes from GitHub into your local branch |
| `git fetch origin` | Download changes from GitHub without merging them yet |
| `git fetch` | Same as `git fetch origin` — downloads remote changes without merging |
| `git merge origin/main` | Merge fetched remote changes into your current local branch |

---

## Remote Branches

| Command | Meaning |
|---------|---------|
| `git branch -a` | List all branches — both local and remote |
| `git branch -r` | List remote branches only |
| `git push -u origin feature-login` | Push a local feature branch to GitHub and set it to track the remote |
| `git push origin feature-login` | Push commits on a feature branch to its remote counterpart on GitHub |
| `git push origin --delete feature-login` | Delete a branch from GitHub (remote) |
| `git checkout -b feature-database origin/feature-database` | Create a local branch that tracks a specific remote branch |
| `git pull upstream main` | Pull latest changes from the original (upstream) repo into your local main |
| `git push origin main` | Push your updated local main branch to your fork on GitHub |

---

## Forking & Open Source Workflow

| Command | Meaning |
|---------|---------|
| `git remote add upstream <original-repo-url>` | Track the original repository (that you forked from) as "upstream" |
| `git checkout -b fix-homepage` | Create a new branch in your fork for your changes |
| `git push origin fix-homepage` | Push your branch to your own fork on GitHub |
| `git pull upstream main` | Pull the latest changes from the original (upstream) repo into your local main |
| `git push origin main` | Sync your fork's main branch on GitHub after pulling from upstream |

---

## gitignore & gitkeep

| Command / Pattern | Meaning |
|---------|---------|
| `filename.txt` (in .gitignore) | Ignore a specific file |
| `folder/` (in .gitignore) | Ignore an entire folder |
| `*.log` (in .gitignore) | Ignore all files ending with .log |
| `temp*` (in .gitignore) | Ignore all files starting with "temp" |
| `!important.log` (in .gitignore) | Exception — do NOT ignore this specific file |
| `git add .gitignore` | Stage the .gitignore file itself |
| `uploads/.gitkeep` (empty file) | Keep an otherwise empty folder tracked by Git (by convention) |


