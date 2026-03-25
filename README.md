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

