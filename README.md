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
1. Set your global author name ☛ git config --global user.name "[firstname lastname]"
```
```bash
2. Set the email associated with your user account ☛ git config --global user.email "[valid-email]"
```
```bash
3. Enable colored CLI output. These values tag your commits and make CLI output easier to read ☛ git config --global color.ui auto
```
```bash
4. Set your default editor git ☛ config --global core.editor "vim"
```
```bash
5. Set your default merge tool ☛ git config --global merge.tool "vimdiff"
```
```bash
6. Set your default push behaviour ☛ git config --global push.default "simple"
```
```bash
7. Set your default push behaviour ☛ git config --global pull.rebase "true"
```
```bash
8. Set your default branch name ☛ git config --global init.defaultBranch "main"
```
```bash
9. Set your default credential helper ☛ git config --global credential.helper "cache --timeout=3600"
```
---

## 3) Initialize or Clone a Repository

```bash
1. git init turns the current folder into a new ☛ git init
```
```bash
2. git clone copies an existing remote repository onto your machine ☛ git clone [url]
```

## 4)Observe your Repository

```bash
1. To list new or modified files not yet committed ☛ git status
```
```bash
2. To show the changes to files not yet staged ☛ git diff
```
```bash
3. To show the changes to staged files ☛ git diff --cached
```
```bash
4. To show all staged and unstaged file changes ☛ git diff HEAD
```
```bash
5. To show the changes between two commit ids ☛ git diff commit1 commit2
```
```bash
6. To list the change dates and authors for a file ☛ git blame [file]
```
```bash
7. To show the file changes for a commit id and/or file ☛ git show [commit]: [file]
```
```bash
8. To show full change history ☛ git log
```
```bash
9. To show the change history for file/directory including diffs ☛ git log -p [file/directory]
```
```bash
10. To show the change history for a specific author ☛ git log --author="[author name]"
```

## 5)Stage & Snapshot (Working Directory ↔ Staging Area ↔ Commit)

```bash
1. To stage the file, ready for commit ☛ git add [file]
```
```bash
2. To stage all changed files, ready for ☛ commit git add .
```
```bash
3. To commit all staged files to the versioned history ☛ git commit -m "commit message"
```
```bash
4. To commit all your tracked files to the versioned history ☛ git commit -am "commit message"
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

- To get the latest changes from the origin (no merge)
```bash
git fetch
```
- To fetch the latest changes from the origin and merge
```bash
git pull
```
- To fetch the latest changes from the origin and rebase
```bash
git pull --rebase
```
- To push local changes to the origin
```bash
git push
```

## 7) Branch & Merge (Isolate Work and Integrate)

- To list all local branches
```bash
git branch
```
- To list remote and local branches
```bash
git branch -a
```
- To switch to an existing branch, branch_name, and update the working directory
```bash
git checkout branch_name
```
- To switch to the last used branch
```bash
git checkout -
```
- To create a new branch called the new branch
```bash
git branch [branch-name]
```
- To create a local branch and switch to it
```bash
git checkout -b branch_name
```
- To delete the branch called my_branch
```bash
git branch -d my_branch
```
- To push a branch to remote
```bash
git push origin branch_name
```
- To rename a current branch
```bash
git branch -m new_name
```
- To merge branch _a into branch_b
```bash
git checkout branch_b git merge branch_a
```
- To abort the current merge
```bash
git merge --abort
```
- To tag the current commit
```bash
git tag my_tag
```
- To discard all local commits and changes
```bash
git reset --hard origin/<remote_branch_name>
```

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
