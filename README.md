# Git Cheat Sheet — README

This README collects the most common Git commands with short, practical explanations so you can copy & paste them directly. It is adapted from the GitHub Education **GIT CHEAT SHEET**.

## 1) Installation (Pointers)
Use your platform’s installer or package manager.
- Git for all platforms: git-scm.com
- GitHub Desktop for Windows/Mac

> Tip: After installation, run `git --version` to verify Git is available.

---

## 2) Setup (Global Identity & UI)

- Set your global author name
```bash
git config --global user.name "[firstname lastname]"
```
- Set the email associated with your user account
```bash
git config --global user.email "[valid-email]"
```
- Enable colored CLI output. These values tag your commits and make CLI output easier to read.
```bash
git config --global color.ui auto
```
- Set your default editor
```bash
git config --global core.editor "vim"
```
- Set your default merge tool
```bash
git config --global merge.tool "vimdiff"
```
- Set your default push behaviour
```bash
git config --global push.default "simple"
```
- Set your default push behaviour
```bash
git config --global pull.rebase "true"
```
- Set your default branch name
```bash
git config --global init.defaultBranch "main"
```
- Set your default credential helper
```bash
git config --global credential.helper "cache --timeout=3600"
```
---

## 3) Initialize or Clone a Repository

- git init turns the current folder into a new Git repository.
```bash
git init
```
- git clone copies an existing remote repository onto your machine.
```bash
git clone [url]
```

## 4)Observe your Repository

- To list new or modified files not yet committed
```bash
git status
```
- To show the changes to files not yet staged
```bash
git diff
```
- To show the changes to staged files
```bash
git diff --cached
```
- To show all staged and unstaged file changes
```bash
git diff HEAD
```
- To show the changes between two commit ids
```bash
git diff commit1 commit2
```
- To list the change dates and authors for a file
```bash
git blame [file]
```
- To show the file changes for a commit id and/or file
```bash
git show [commit]: [file]
```
- To show full change history
```bash
git log
```
- To show the change history for file/directory including diffs
```bash
git log -p [file/directory]
```
- To show the change history for a specific author
```bash
git log --author="[author name]"
```

## 5)Stage & Snapshot (Working Directory ↔ Staging Area ↔ Commit)

- To stage the file, ready for commit
```bash
git add [file]
```
- To stage all changed files, ready for commit
```bash
git add .
```
- To commit all staged files to the versioned history
```bash
git commit -m "commit message"
```
- To commit all your tracked files to the versioned history
```bash
git commit -am "commit message"
```
- To set the executable flag to a file foo.sh
```bash
git update-index --chmod=+x foo.sh
```
- To unstaged the file, keeping the file changes
```bash
git reset [file]
```
- To revert everything to the last commit
```bash
git reset --hard
```
- To overwrite commit history with your local history (force push)
```bash
git push --force
```
- To reset remote branch to specific commit (danger: use only if not distributed to other people before)
```bash
git reset --hard <commit-hash> && git push -f origin <branch-name>
```

## 6) Synchronize

```bash
git fetch
```bash
git pull
```bash
git pull --rebase
git push
```
- To get the latest changes from the origin (no merge)
- To fetch the latest changes from the origin and merge
- To fetch the latest changes from the origin and rebase
- To push local changes to the origin

## 7) Branch & Merge (Isolate Work and Integrate)

```bash
git branch
git branch -a
git checkout branch_name
git checkout -
git branch [branch-name]
git checkout -b branch_name
git branch -d my_branch
git push origin branch_name
git branch -m new_name
git checkout branch_b git merge branch_a
git merge --abort
git tag my_tag
git reset --hard origin/<remote_branch_name>
```
- To list all local branches
- To list remote and local branches
- To switch to an existing branch, branch_name, and update the working directory
- To switch to the last used branch
- To create a new branch called the new branch
- To create a local branch and switch to it
- To delete the branch called my_branch
- To push a branch to remote
- To rename a current branch
- To merge branch _a into branch_b
- To abort the current merge
- To tag the current commit
- To discard all local commits and changes

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
