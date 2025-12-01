# Git Cheat Sheet — README

This README collects the most common Git commands with short, practical explanations so you can copy & paste them directly. It is adapted from the GitHub Education **GIT CHEAT SHEET**.

## 📦 Installation (Pointers)
Use your platform’s installer or package manager.
- Git for all platforms: git-scm.com
- GitHub Desktop for Windows/Mac

> Tip: After installation, run `git --version` to verify Git is available.

---

## ⚙️ Setup (Global Identity & UI)

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

## 📁 Initialize or Clone a Repository

```bash
1. git init turns the current folder into a new ☛ git init
```
```bash
2. git clone copies an existing remote repository onto your machine ☛ git clone [url]
```

## 👀 Observe your Repository

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

## 📝 Stage & Snapshot (Working Directory ↔ Staging Area ↔ Commit)

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
```bash
5. To set the executable flag to a file foo.sh ☛ git update-index --chmod=+x foo.sh
```
```bash
6. To unstaged the file, keeping the file changes ☛ git reset [file]
```
```bash
7. To revert everything to the last commit ☛ git reset --hard
```
```bash
8. To overwrite commit history with your local history (force push) ☛ git push --force
```
```bash
10. To reset remote branch to specific commit (danger: use only if not distributed to other people before) ☛ git reset --hard <commit-hash> && git push -f origin <branch-name>
```

## 🔄 Synchronize

```bash
1. To get the latest changes from the origin (no merge) ☛ git fetch
```
```bash
2. To fetch the latest changes from the origin and merge ☛ git pull
```
```bash
3. To fetch the latest changes from the origin and rebase ☛ git pull --rebase
```
```bash
4. To push local changes to the origin ☛ git push
```

## 🌿 Branch & Merge (Isolate Work and Integrate)

```bash
1. To list all local branches ☛ git branch
```
```bash
2. To list remote and local branches ☛ git branch -a
```
```bash
3. To switch to an existing branch, branch_name, and update the working directory ☛ git checkout branch_name
```
```bash
4. To switch to the last used branch ☛ git checkout
```
```bash
5. To create a new branch called the new branch ☛ git branch [branch-name]
```
```bash
6. To create a local branch and switch to it ☛ git checkout -b branch_name
```
```bash
7. To delete the branch called my_branch ☛ git branch -d my_branch
```
```bash
8, To push a branch to remote ☛ git push origin branch_name
```
```bash
9. To rename a current branch ☛ git branch -m new_name
```
```bash
10. To merge branch _a into branch_b ☛ git checkout branch_b git merge branch_a
```
```bash
11. To abort the current merge git ☛ merge --abort
```
```bash
12. To tag the current commit ☛ git tag my_tag
```
```bash
13. To discard all local commits and changes ☛ git reset --hard origin/<remote_branch_name>
```

## 🚀 Share & Update (Remotes)

```bash
1. To add names a remote (e.g., origin) for a URL ☛ git  remote add [alias] [url]
```
```bash
2. To downloads branches/commits from that remote ☛ git fetch [alias]
```
```bash
3. To brings a remote branch into your current branch ☛ git merge [alias]/[branch]
```
```bash
4. To uploads your local commits to the remote branch ☛ git push [alias] [branch]
```
```bash
5. To fetch + merge from the tracking branch ☛ git pull
```

## 🛣️ Tracking Path Changes (Rename / Delete Files)

```bash
1. To removes a file and stages the deletion ☛ git rm [file]
```
```bash
2. To renames/moves a file and stages the move ☛ git mv [existing-path] [new-path]
```
```bash
3. To shows commit logs and indicates moved/renamed paths ☛ git log --stat -M
```

## ✂️ Rewrite History

```bash
1. To replays current branch commits on top of the specified branch (linear history) ☛ git rebase [branch]
```
```bash
2. moves HEAD and resets both index and working tree to the given commit (discarding local changes) ☛ git reset --hard [commit]
```

## 🔍 Inspect & Compare

```bash
1. To view commit history ☛ git log
```
```bash
2. To show commit history in single lines: git log --oneline
```
```bash
3. To show the commit history for the last N commits: git log -2
```
```bash
4. To show commit history for the last N commits with diff: git log -p -2
```
```bash
5. To show reflog history for emergency actions: git reflog
```
```bash
6, To show all local file changes in the working tree: git diff
```
```bash
7. To show changes made to a file: git diff myfile
```
```bash
7. To show who changed what & when in a file: git blame myfile
```
```bash
8. To show remote branches and their mapping to local: git remote show origin
```
```bash
9. To view commits in branchA not in branchB ☛ git log branchB..branchA
```
```bash
10. To view what’s in branchA that isn’t in branchB ☛ git diff branchB...branchA
```
```bash
11. To traces a file’s history across renames ☛ git log --follow [file]
```
```bash
12. To view an object (commit, tag, tree, blob) in readable form ☛ git show [SHA]
```

## 🧹 Clean Up
```bash
1. To delete all untracked files ☛ git clean -f
```
```bash
2. To delete all untracked files and directories ☛ git clean -df
```
```bash
3. To undo local modifications to all files ☛ git checkout --
```
```bash
4. To unstaged a file ☛ git reset HEAD myfile
```
```bash
5. To undo local modifications to a file and stage it ☛ git checkout -- myfile git add myfile
```
```bash
6, To find the commit that introduced a bug ☛ git bisect start git bisect bad git bisect good <commit>

```
## 🧩 Submodules
```bash
1. To add a submodule ☛ git submodule add <url>
```
```bash
2. To update a submodule ☛ git submodule update --remote
```
```bash
3. To remove a submodule ☛ git submodule deinit -f -- submodule_name git rm -f submodule_name git rm -f .gitmodules
```

## 🌳 Subtrees
```bash
1. To add a subtree ☛ git subtree add --prefix=folder_name <url>
```
```bash
2. To update a subtree ☛ git subtree pull --prefix=folder_name <url>
```
```bash
3. To remove a subtree ☛ git subtree split --prefix=folder_name git rm -rf folder_name git commit -m "Remove folder_name"
```

## 📥 Stash
```bash
1. Stash Changes with a message git stash save "message"
```
```bash
2. List all stashes git stash list
```
```bash
3. Apply the most recent stash and remove it from the stash list. git stash pop
```

## 🙈 Ignoring Files

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

## ❓ Help

```git help -a``` and ```git help -g``` list available subcommands and some
concept guides. See ```git help <command>``` or ```git help <concept>```
to read about a specific subcommand or concept.
See ```git help git``` for an overview of the system.
<br>

## 🌐 Git Resources
You should check some of these Git resources as they would be amazing for your journey.
You will master Git with these resources:

#### ⭐ [Oh My Git](https://ohmygit.org/)
This is an open-source card game that is dedicated to teaching important git commands. There's even an integrated terminal for you to test any git command you wish. Their graphics are nothing fancy but it helps with learning visually.

#### ⭐ [The Odin Project](https://www.theodinproject.com/lessons/foundations-git-basics)
This site provides free full-stack courses that are maintained by the open-source community. They have two git courses that are well worth your attention.

#### ⭐ [Learn Git Branching](https://learngitbranching.js.org/)
Branching is an important topic in Git. There's no better way to learn it than this interactive game. Run commands with their built-in terminal and let their graphics explain the rest.

#### ⭐ [Git Tutorial by Atlasian](https://www.atlassian.com/git/tutorials)
Become a git guru with the help of Atlassian tutorials. Atlassian has done a fantastic job with their explanations and visuals to understand git. This is one of the top resources for learning Git.

#### ⭐ [Git Immersion](https://gitimmersion.com/)
Learn all the fundamentals of Git with this guided tour. This resource explains every important Git command while you execute them on your local machine.

#### ⭐ [Visual Git Reference](https://marklodato.github.io/visual-git-guide/index-en.html)
I'm a big believer that visual aids help you better understand and remember information. Which is why this resource is a must-see. Their diagrams and explanations are top-tier.

#### ⭐ [GitHub Minesweeper](https://profy.dev/project/github-minesweeper)
Get a dose of nostalgia with this one! Learn on-the-job Git workflow while playing minesweeper with another player. So much fun you'll forget you're even learning.

## Are you more of an extensive reader, I got you!

For more in-depth reading - you should check Git Notes for Professionals 📕
- [Git Notes for Professionals by GoalKicker](https://goalkicker.com/GitBook/GitNotesForProfessionals.pdf)


### If this project helped you in any way, please consider giving it a ⭐️. It will help us reach more people and help them learn Git & GitHub.

