# The "Universal" Git Lifecycle
Regardless of the command, the flow is almost always:

To understand the universal Git lifecycle, you have to look past the commands and see Git as a content-addressable filesystem. Regardless of whether you are merging, rebasing, or simply committing, Git follows a rigid internal "pipeline" to process data.

Here is the high-level architecture of that lifecycle.

## 1. The Trinity of States
Every action in Git moves data between three distinct areas. Understanding the "Universal Lifecycle" is essentially understanding the movement between these three zones:

- The Working Directory: The actual files on your disk (MacBook, Linux, etc.). These are "untracked" or "modified."
- The Index (Staging Area): A single binary file at `.git/index`. It is a "technical draft" of your next commit.
- The Object Database (The Repository): The permanent, compressed storage in `.git/objects`.
