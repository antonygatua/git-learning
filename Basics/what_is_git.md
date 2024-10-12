# What is Git?

Understanding Git and its fundamentals makes it easier to use it effectively. Git is a distributed version control system (VCS) designed to handle everything from small to very large projects with speed and efficiency.

## Snapshots, Not Differences

Conceptually, most other version control systems (VCS), such as Subversion (SVN), store information as a list of changes per file over time—commonly described as *delta-based version control*. 

![delta](../resources/deltas.png)

`figure 1. Storing data as changes to a base version of each file`

Git, however, handles data differently. It takes a snapshot of the entire file system each time you commit or save the state of your project. If files haven't changed, Git doesn’t store the files again but creates a reference to the previous version for efficiency. Essentially, Git sees your data as a series of snapshots of your file system.

![snapshots](../resources/snapshots.png)

`figure 2. Storing data as snapshots of the project over time`

---
## Nearly Every Operation is Local

Most operations in Git only require local files and resources. This means that almost all operations do not need information from a remote server, making Git very fast and efficient. The entire project history is stored locally, so browsing the project’s history, for instance, doesn’t require accessing the network; it reads directly from the local database.

Git’s local-first nature means that you can do almost everything offline. You can make commits to your local copy and sync them with the remote server later when you have a network connection. This is not the case with many other systems. For example:
- In Perforce, you can't do much if you aren’t connected to the server.
- In Subversion, you can edit files, but you can't commit changes without server access.

---
## Git Has Integrity

Everything in Git is checksummed before it is stored, and Git refers to it using this checksum. *A **checksum** is a calculated value based on the contents of a file or directory structure to ensure data integrity.* 

The mechanism Git uses for checksumming is called a **SHA-1 hash**. This hash is a 40-character string (composed of numbers 0-9 and letters a-f) derived from the contents of the file or directory structure. A SHA-1 hash looks something like:

```
24b9da655252987aa493b52f869cd6d3b00373
```

Git stores everything in its database using the hash value rather than the file name, ensuring that any changes to file contents are tracked.

---
## Git Generally Only Adds Data

Almost all operations in Git add data to the database. It is designed to prevent data loss, making it difficult to perform irreversible actions or delete data unintentionally.

---
## The Three States

Git tracks your files in three main states: **Modified**, **Staged**, and **Committed**.

1. **Modified**: You have changed the file but have not yet staged it.
2. **Staged**: The modified file is marked to be included in the next commit snapshot.
3. **Committed**: The data is safely stored in your local Git database.

These states relate to the three main sections of a Git project: **the Working Tree**, **the Staging Area**, and the **Git Directory**.

![git states](../resources/areas.png)
`figure 3. Working tree, staging area, and Git directory`

### 1. Working Tree

The working tree is a single checkout of one version of the project. These files are pulled from the compressed database in the Git directory and placed on disk for you to modify.

### 2. Staging Area

The staging area (or *index*) is a file within your Git directory that stores information about what will be included in your next commit. It acts as a preparation space before you finalize your changes.

### 3. Git Directory

The Git directory is where Git stores the metadata and object database for your project. It’s the most crucial part of Git, and when you clone a repository, you’re copying the contents of this directory.

---
### Basic Workflow

The typical workflow in Git involves the following steps:

1. Modify files in your working tree.
2. Stage changes selectively, adding only those modifications you want to include in your next commit to the staging area.
3. Commit the staged changes, which stores a snapshot of the files permanently in your Git directory.

If a file is in the Git directory, it’s **committed**.  
If a file has been modified and added to the staging area, it’s **staged**.  
If a file has been changed but not yet staged, it’s **modified**.

---