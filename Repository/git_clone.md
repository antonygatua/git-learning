# `git clone`

The `git clone` command is the primary way to obtain a development copy of an existing project from a central repository. It’s usually performed once to set up the project locally. After cloning, all subsequent interactions (commits, pulls, pushes) occur within the local repository. 

### Repo-to-Repo Collaboration

Git's approach to "working copies" is distinct from systems like SVN. In SVN, the working copy is tied directly to the central repository. Git, however, treats each cloned repository as a full-fledged, independent copy. Every clone contains the entire project history and acts as its own version-controlled environment.

In SVN, interactions are centralized (checked out and committed back to a central repository). Git, on the other hand, uses a repository-to-repository model for collaboration. Developers push and pull changes between repositories rather than syncing with a singular, central repository.

However, a central repository can still be established in Git through convention rather than necessity. Developers designate a "central" repository and follow workflows that push and pull changes, replicating a centralized model.

---

## Usage

`git clone` allows developers to create a full copy of an existing repository, which can be either local or remote. This cloned copy has its own history and functions independently from the original repository, unlike SVN’s approach.

When you clone, Git automatically sets up a remote connection named "origin" that points back to the source repository. This simplifies future interactions with the source, such as pulling updates.

### Example Usage

To clone a repository via SSH:

```bash
git clone ssh://john@example.com/path/to/my-project.git 
cd my-project
# Start working on the project
```

The first command initializes a new Git repository (`my-project`) and copies its contents locally. From there, you can start editing, committing, and pushing changes.

**Note:** The `.git` extension is often omitted in non-bare repositories, as it signifies a working directory (development environment).

---

## Cloning Variations

### Clone to a Specific Folder

```bash
git clone <repo> <directory>
```

Clones the repository located at `<repo>` into the specified `<directory>` on the local machine.

### Clone a Specific Tag

```bash
git clone --branch <tag> <repo>
```

This clones the repository and only includes the branch or tag specified by `<tag>`.

### Shallow Clone

```bash
git clone --depth=1 <repo>
```

Clones only the most recent commit from the repository. Shallow clones are useful for large repositories with extensive histories, reducing disk usage and speeding up the cloning process.

---

## Configuration Options

### `--branch`

```bash
git clone --branch <branch> <repo>
```

Allows you to clone a specific branch instead of the default branch that the remote `HEAD` points to. Tags can also be specified.

### `--bare` vs. `--mirror`

- **`--bare`**: Creates a repository without a working directory, suitable for remote sharing (pushing/pulling only).
  
- **`--mirror`**: Similar to `--bare`, but also copies all refs and maintains remote branch tracking. Useful for creating an exact mirror of the original repository.

### `--template`

```bash
git clone --template=<template_directory> <repo>
```

Applies a specified template during cloning, initializing the new repository with predefined configurations or hooks.

---

## Git URLs and Protocols

Git uses several URL protocols to access remote repositories:

1. **SSH** (`ssh://[user@]host.xz[:port]/path/to/repo.git`): Common and secure; requires authentication setup.

2. **Git** (`git://host.xz[:port]/path/to/repo.git`): A unique, unauthenticated protocol using Git’s daemon (port 9418).

3. **HTTP/HTTPS** (`http[s]://host.xz[:port]/path/to/repo.git`): Uses the standard web protocol; authentication may be required.

---

## Summary

- `git clone` copies an existing repository, either local or remote.
- The command supports several protocols and options for flexibility.
- Cloning creates a fully functional, independent Git repository.
- Various configuration options adjust how and what content is cloned.