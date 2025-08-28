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
```
- Set your global author name and email, and enable colored CLI output. These values tag your commits and make CLI output easier to read.
---

## 3) Initialize or Clone a Repository

```bash
git init
git clone [url]
```
- git init turns the current folder into a new Git repository.
- git clone copies an existing remote repository onto your machine.

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
