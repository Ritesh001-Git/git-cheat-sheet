# Git Cheat Sheet — README

This README collects the most common Git commands with short, practical explanations so you can copy & paste them directly. It is adapted from the GitHub Education **GIT CHEAT SHEET**.

## 1) Installation (Pointers)
Use your platform’s installer or package manager. The original cheat sheet references:
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

---

## 3) Initialize or Clone a Repository

```bash
git init
git clone [url]
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

## 5) Branch & Merge (Isolate Work and Integrate)

```bash
git branch
git branch [branch-name]
git checkout [branch-name]
git merge [branch]
git log
```
