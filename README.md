# Git Cheat Sheet — README

This README collects the most common Git commands with short, practical explanations so you can copy & paste them directly. It is adapted from the GitHub Education **GIT CHEAT SHEET**.

## 1) Installation (Pointers)
Use your platform’s installer or package manager.
- Git for all platforms: git-scm.com
- GitHub Desktop for Windows/Mac

> Tip: After installation, run `git --version` to verify Git is available.

---

## 2) Setup (Global Identity & UI)

```bash
git config --global user.name "[firstname lastname]"
git config --global user.email "[valid-email]"
git config --global color.ui auto
git config --global core.editor "vim"
git config --global merge.tool "vimdiff"
git config --global push.default "simple"
git config --global pull.rebase "true"
git config --global init.defaultBranch "main"
git config --global credential.helper "cache --timeout=3600"
```
- Set your global author name
- Set the email associated with your user account
- Enable colored CLI output. These values tag your commits and make CLI output easier to read.
- Set your default editor
- Set your default merge tool
- Set your default push behaviour
- Set your default pull behaviour
- Set your default branch name
- Set your default credential helper
---

## 3) Initialize or Clone a Repository

```bash
git init
git clone [url]
```
- git init turns the current folder into a new Git repository.
- git clone copies an existing remote repository onto your machine.

## 4)Observe your Repository

```bash
git status
git diff
git diff --cached
git diff HEAD
git diff commit1 commit2
git blame [file]
git show [commit]: [file]
git log
```
## 4)Stage & Snapshot (Working Directory ↔ Staging Area ↔ Commit)

```bash
git status
git add .
git add [file]
git reset [file]
git diff
git diff --staged
git commit -m "[descriptive message]"
```
- git status shows what’s modified/staged.
- git add stages file(s) for the next commit.
- git reset [file] unstages (keeps your changes in the working directory).
- git diff shows unstaged changes.
- git diff --staged shows staged-but-uncommitted changes.
- git commit -m creates a new snapshot of staged changes.

## 5) Branch & Merge (Isolate Work and Integrate)

```bash
git branch
git branch [branch-name]
git checkout [branch-name]
git merge [branch]
git log
```
- git branch lists branches (the current branch has a *).
- git branch [name] creates a new branch at the current commit.
- git checkout [name] switches your working directory to that branch.
- git merge [branch] merges the named branch into the current one.
- git log shows the commit history of the current branch.

## 6) Share & Update (Remotes)

```bash
git remote add [alias] [url]
git fetch [alias]
git merge [alias]/[branch]
git push [alias] [branch]
git pull
```
- git remote add names a remote (e.g., origin) for a URL.
- git fetch downloads branches/commits from that remote.
- merge [alias]/[branch] brings a remote branch into your current branch.
- git push uploads your local commits to the remote branch.
- git pull = fetch + merge from the tracking branch.

## 7) Tracking Path Changes (Rename / Delete Files)

```bash
git rm [file]
git mv [existing-path] [new-path]
git log --stat -M
```
- git rm removes a file and stages the deletion.
- git mv renames/moves a file and stages the move.
- git log --stat -M shows commit logs and indicates moved/renamed paths.

## 8) Rewrite History

```bash
git rebase [branch]
git reset --hard [commit]
```
- git rebase replays current branch commits on top of the specified branch (linear history).
- git reset --hard moves HEAD and resets both index and working tree to the given commit (discarding local changes).

## 8) Inspect & Compare

```bash
git log
git log branchB..branchA
git log --follow [file]
git diff branchB...branchA
git show [SHA]
```
- git log shows commit history.
- git log branchB..branchA shows commits in branchA not in branchB.
- git log --follow [file] traces a file’s history across renames.
- git diff branchB...branchA shows what’s in branchA that isn’t in branchB.
- git show [SHA] displays an object (commit, tag, tree, blob) in readable form.

## 9) Ignoring Files

Global ignore file:
``` bash
git config --global core.excludesfile [file]
```

Repository-local ignore patterns (create a .gitignore):
``` bash
logs/
*.notes
.env/
```
- Set a global ignore file for patterns you always want ignored.
- Use a repository .gitignore to keep temporary/build files out of commits. 
