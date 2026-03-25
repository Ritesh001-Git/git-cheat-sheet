# Git Cheat Sheet — README

This README collects the most common Git commands with short, practical explanations so you can copy & paste them directly. It is adapted from the GitHub Education **GIT CHEAT SHEET**.

## 📑 Table of Contents

* [📦 Installation](https://github.com/Ritesh001-Git/git-cheat-sheet?tab=readme-ov-file#-installation-pointers)
* [⚙️ Setup (Global Identity & UI)](https://github.com/Ritesh001-Git/git-cheat-sheet?tab=readme-ov-file#%EF%B8%8F-setup-global-identity--ui)
* [📁 Initialize or Clone a Repository](https://github.com/Ritesh001-Git/git-cheat-sheet?tab=readme-ov-file#-initialize-or-clone-a-repository)
* [👀 Observe your Repository](https://github.com/Ritesh001-Git/git-cheat-sheet?tab=readme-ov-file#-observe-your-repository)
* [📝 Stage & Snapshot](https://github.com/Ritesh001-Git/git-cheat-sheet?tab=readme-ov-file#-stage--snapshot-working-directory--staging-area--commit)
* [🔄 Synchronize](https://github.com/Ritesh001-Git/git-cheat-sheet?tab=readme-ov-file#-synchronize)
* [🌿 Branch & Merge](https://github.com/Ritesh001-Git/git-cheat-sheet?tab=readme-ov-file#-branch--merge-isolate-work-and-integrate)
* [🚀 Share & Update (Remotes)](https://github.com/Ritesh001-Git/git-cheat-sheet?tab=readme-ov-file#-share--update-remotes)
* [🛣️ Tracking Path Changes](https://github.com/Ritesh001-Git/git-cheat-sheet?tab=readme-ov-file#%EF%B8%8F-tracking-path-changes-rename--delete-files)
* [✂️ Rewrite History](https://github.com/Ritesh001-Git/git-cheat-sheet?tab=readme-ov-file#%EF%B8%8F-rewrite-history)
* [🔍 Inspect & Compare](https://github.com/Ritesh001-Git/git-cheat-sheet?tab=readme-ov-file#-inspect--compare)
* [🧹 Clean Up](https://github.com/Ritesh001-Git/git-cheat-sheet?tab=readme-ov-file#-clean-up)
* [🧩 Submodules](https://github.com/Ritesh001-Git/git-cheat-sheet?tab=readme-ov-file#-submodules)
* [🌳 Subtrees](https://github.com/Ritesh001-Git/git-cheat-sheet?tab=readme-ov-file#-subtrees)
* [📥 Stash](https://github.com/Ritesh001-Git/git-cheat-sheet?tab=readme-ov-file#-stash)
* [🙈 Ignoring Files](https://github.com/Ritesh001-Git/git-cheat-sheet?tab=readme-ov-file#-ignoring-files)
* [❓ Help](https://github.com/Ritesh001-Git/git-cheat-sheet?tab=readme-ov-file#-help)
* [🌐 Git Resources](https://github.com/Ritesh001-Git/git-cheat-sheet?tab=readme-ov-file#-git-resources)

## 📦 Installation (Pointers)
Use your platform’s installer or package manager.
- Git for all platforms: git-scm.com
- GitHub Desktop for Windows/Mac

> Tip: After installation, run `git --version` to verify Git is available.

---

## ⚙️ Setup (Global Identity & UI)

Command | Description | Example
--- | --- | ---
`git config --global user.name "[firstname lastname]"` | set global username | `git config --global user.name "Ritesh Swain"`
`git config --global user.email "[valid-email]"` | set global email | `git config --global user.email "abc@gmail.com"`
`git config --global color.ui auto` | enable colored CLI output | `git config --global color.ui auto`
`git config --global core.editor "vim"` | set default editor | `git config --global core.editor "vim"`
`git config --global merge.tool "vimdiff"` | set merge tool | `git config --global merge.tool "vimdiff"`
`git config --global push.default "simple"` | set default push behavior | `git config --global push.default simple`
`git config --global pull.rebase "true"` | enable rebase on pull | `git config --global pull.rebase true`
`git config --global init.defaultBranch "main"` | set default branch | `git config --global init.defaultBranch main`
`git config --global credential.helper "cache --timeout=3600"` | cache credentials | `git config --global credential.helper "cache --timeout=3600"`

---

## 📁 Initialize or Clone a Repository

Command | Description | Example
--- | --- | ---
`git init` | initialize new repository | `git init`
`git clone [url]` | clone remote repo | `git clone https://github.com/user/repo.git`

---

## 👀 Observe your Repository

Command | Description | Example
--- | --- | ---
`git status` | show working directory status | `git status`
`git diff` | show unstaged changes | `git diff`
`git diff --cached` | show staged changes | `git diff --cached`
`git diff HEAD` | show all changes | `git diff HEAD`
`git diff commit1 commit2` | compare commits | `git diff a1b2 c3d4`
`git blame [file]` | show author per line | `git blame app.js`
`git show [commit]:[file]` | show file in commit | `git show abc123:app.js`
`git log` | show commit history | `git log`
`git log -p [file]` | show history with diff | `git log -p app.js`
`git log --author="name"` | filter by author | `git log --author="Ritesh"`

---

## 📝 Stage & Snapshot

Command | Description | Example
--- | --- | ---
`git add [file]` | stage file | `git add index.js`
`git add .` | stage all files | `git add .`
`git commit -m "msg"` | commit staged changes | `git commit -m "init"`
`git commit -am "msg"` | commit tracked files | `git commit -am "update"`
`git update-index --chmod=+x file` | make file executable | `git update-index --chmod=+x script.sh`
`git reset [file]` | unstage file | `git reset index.js`
`git reset --hard` | reset all changes | `git reset --hard`
`git push --force` | force push | `git push --force`
`git reset --hard <hash> && git push -f origin <branch>` | reset remote branch | `git reset --hard abc123 && git push -f origin main`

---

## 🔄 Synchronize

Command | Description | Example
--- | --- | ---
`git fetch` | fetch remote changes | `git fetch`
`git pull` | fetch + merge | `git pull`
`git pull --rebase` | fetch + rebase | `git pull --rebase`
`git push` | push changes | `git push`

---

## 🌿 Branch & Merge

Command | Description | Example
--- | --- | ---
`git branch` | list branches | `git branch`
`git branch -a` | list all branches | `git branch -a`
`git checkout branch` | switch branch | `git checkout dev`
`git checkout` | switch last branch | `git checkout`
`git branch name` | create branch | `git branch feature`
`git checkout -b name` | create + switch | `git checkout -b feature`
`git branch -d name` | delete branch | `git branch -d feature`
`git push origin branch` | push branch | `git push origin feature`
`git branch -m new` | rename branch | `git branch -m main`
`git merge branch` | merge branch | `git merge dev`
`git merge --abort` | abort merge | `git merge --abort`
`git tag tag` | create tag | `git tag v1.0`
`git reset --hard origin/branch` | discard local changes | `git reset --hard origin/main`

---

## 🚀 Share & Update (Remotes)

Command | Description | Example
--- | --- | ---
`git remote add name url` | add remote | `git remote add origin url`
`git fetch name` | fetch remote | `git fetch origin`
`git merge name/branch` | merge remote | `git merge origin/main`
`git push name branch` | push to remote | `git push origin main`
`git pull` | fetch + merge | `git pull`

---

## 🛣️ Tracking Path Changes

Command | Description | Example
--- | --- | ---
`git rm file` | delete file | `git rm app.js`
`git mv old new` | rename file | `git mv a.txt b.txt`
`git log --stat -M` | show renamed files | `git log --stat -M`

---

## ✂️ Rewrite History

Command | Description | Example
--- | --- | ---
`git rebase branch` | rebase commits | `git rebase main`
`git reset --hard commit` | reset to commit | `git reset --hard abc123`

---

## 🔍 Inspect & Compare

Command | Description | Example
--- | --- | ---
`git log` | show history | `git log`
`git log --oneline` | compact log | `git log --oneline`
`git log -2` | last 2 commits | `git log -2`
`git log -p -2` | commits with diff | `git log -p -2`
`git reflog` | show reflog | `git reflog`
`git diff` | show changes | `git diff`
`git diff file` | diff file | `git diff app.js`
`git blame file` | blame file | `git blame app.js`
`git remote show origin` | show remote info | `git remote show origin`
`git log A..B` | commits diff | `git log main..dev`
`git diff A...B` | diff branches | `git diff main...dev`
`git log --follow file` | track file history | `git log --follow app.js`
`git show SHA` | show object | `git show abc123`

---

## 🧹 Clean Up

Command | Description | Example
--- | --- | ---
`git clean -f` | remove untracked files | `git clean -f`
`git clean -df` | remove files + dirs | `git clean -df`
`git checkout --` | discard changes | `git checkout --`
`git reset HEAD file` | unstage file | `git reset HEAD app.js`
`git checkout -- file && git add file` | reset + stage | `git checkout -- app.js && git add app.js`
`git bisect start` | start bisect | `git bisect start`

---

## 🧩 Submodules

Command | Description | Example
--- | --- | ---
`git submodule add url` | add submodule | `git submodule add repo-url`
`git submodule update --remote` | update submodule | `git submodule update --remote`
`git submodule deinit -f` | remove submodule | `git submodule deinit -f module`

---

## 🌳 Subtrees

Command | Description | Example
--- | --- | ---
`git subtree add --prefix=dir url` | add subtree | `git subtree add --prefix=app repo`
`git subtree pull --prefix=dir url` | update subtree | `git subtree pull --prefix=app repo`
`git subtree split --prefix=dir` | split subtree | `git subtree split --prefix=app`

---

## 📥 Stash

Command | Description | Example
--- | --- | ---
`git stash save "msg"` | stash changes | `git stash save "work"`
`git stash list` | list stashes | `git stash list`
`git stash pop` | apply + remove stash | `git stash pop`

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


### If this cheat sheet helped you in any way, please consider giving it a ⭐️. It will help us reach more people and help them learn Git & GitHub.

