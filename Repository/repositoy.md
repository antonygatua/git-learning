# What is a Repository?

A repository is a storage location for your project's code, documentation, and other files. It serves as the central hub for collaboration, version control, and code management, enabling multiple people to work on the same project without overwriting each other’s code.

In Git, a repository is the `.git/` folder inside a project directory. This folder contains all the information Git needs to track changes, store the project’s history, and manage versions. If the `.git/` folder is deleted, the project's history and version control information are lost, essentially resetting the project to an untracked state.

## Types of Repositories

There are two main types of repositories in Git:

1. **Local Repository**:
    
    - This is the repository located on your local machine. It is where you make changes, stage files, and commit updates. The local repository contains all the project’s history and allows you to work independently without needing an internet connection.
2. **Remote Repository**:
    
    - A remote repository is a version of your repository hosted on a server (e.g., GitHub, GitLab, Bitbucket). It serves as the central location where collaborators can push and pull changes. Remote repositories enable distributed collaboration, making it easy to sync changes across multiple machines and users.