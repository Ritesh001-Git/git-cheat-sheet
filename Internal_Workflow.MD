# The "Universal" Git Lifecycle
Regardless of the command, the flow is almost always:

To understand the universal Git lifecycle, you have to look past the commands and see Git as a content-addressable filesystem. Regardless of whether you are merging, rebasing, or simply committing, Git follows a rigid internal "pipeline" to process data.

Here is the high-level architecture of that lifecycle.

## 1. The Trinity of States
Every action in Git moves data between three distinct areas. Understanding the "Universal Lifecycle" is essentially understanding the movement between these three zones:

- The Working Directory: The actual files on your disk (MacBook, Linux, etc.). These are "untracked" or "modified."
- The Index (Staging Area): A single binary file at `.git/index`. It is a "technical draft" of your next commit.
- The Object Database (The Repository): The permanent, compressed storage in `.git/objects`.

 ##2. The Step-by-Step Internal Lifecycle

### Stage A: Content Hashing (The "Identity" Phase)
When data moves from your Working Directory to the Index (e.g., via git add), Git doesn't just copy the file.

- Action: It reads the file content and calculates a SHA-1 Hash.
- Result: This hash is the "address" of that file. If two files in different folders have the same content, Git only stores them once.
- Storage: The content is compressed and saved as a Blob (Binary Large Object) in the database.

### Stage B: Tree Building (The "Structure" Phase)
Once you trigger a state change (like git commit), Git needs to record the "shape" of your project.

- Action: It look at the Index and groups those file hashes into Tree Objects.
- Hierarchy: A Tree object acts like a folder. It contains a list of hashes (pointing to Blobs) and names.
- Result: This creates a snapshot of the entire project structure at that exact moment.

### Stage C: Snapshotting (The "Context" Phase)
Now that Git has the files (Blobs) and the folders (Trees), it needs to know why and when this happened.

- Action: It creates a Commit Object.
- Linking: This object points to the Root Tree (the top-level folder) and, crucially, to the hash of the Parent Commit.
- Chain: This "Parent Pointer" is what creates the "Git Chain" or history. Without it, you just have random snapshots.

### Stage D: Reference Updating (The "Pointer" Phase)
The final step in every command is moving the "labels."

- Action: Git updates a simple text file in .git/refs/heads/.
- Result: If you are on the main branch, the file main is updated to contain the 40-character SHA-1 hash of the new Commit Object you just created.
- HEAD: The HEAD pointer is then updated to let Git know where you are currently standing.

# The git add, commit & push workflow

## 1. The git add Phase (Indexing)
When you run git add file.txt, Git doesn't just "mark" the file. It performs a massive internal operation:

- Hashing: Git takes the content of your file and runs it through a SHA-1 hashing algorithm. This creates a unique 40-character string (e.g., 5d4140...).
- Blob Creation: It creates a Blob object (Binary Large Object) containing your file data and stores it in `.git/objects`.
- The Index Update: It updates the Index (a binary file at `.git/index)`. The Index is the "Stage." It maps your filename to that specific SHA-1 hash.

## 2. The git commit Phase (Snapshotting)
When you run git commit -m "Initial", Git solidifies the state of the Index into a permanent record.

- Tree Creation: Git creates a Tree object. This is essentially a "directory listing." It points to the Blobs (files) and other Trees (subfolders) that make up your project at that exact moment.
- Commit Object: Git creates a Commit object. This tiny text file contains:

  - The hash of the Tree (the snapshot).
  - The hash of the Parent Commit (the previous state).
  - Metadata: Author, timestamp, and your message.

- Moving the Pointer: Finally, Git updates the Branch Pointer (e.g., refs/heads/main) to point to the hash of this new Commit object.

3. The git push Phase (The Negotiation)
This is where the communication with GitHub (the remote) happens. It follows a protocol called the Smart HTTP or SSH Transport Protocol.

- The Handshake: Your local Git client connects to the GitHub server.
- Discovery: GitHub sends a list of all the commit hashes it currently has for that branch.
- The Negotiation: Your local Git compares GitHub’s list with your local history. It identifies exactly which Commit, Tree, and Blob objects GitHub is missing.
- The Packfile: To save bandwidth, Git doesn't send files one by one. It compresses all the missing objects into a single file called a Packfile.
- The Send: Your client runs a process called send-pack, and GitHub runs receive-pack. The Packfile is sent over the wire.
- Updating the Remote Ref: Once GitHub receives and verifies the data, it moves its own branch pointer (refs/heads/main) to match your new commit hash.
