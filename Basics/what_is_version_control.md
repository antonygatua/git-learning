# Version Control
## What is version control?
Refers to a general concept of managing changes to files over time. It is the idea of organizing, controlling and keeping track of different versions in history of computer files, primarily source code text files, but generally any type of file, allowing one to revert to a previous state if necessary.
## What is a version control system?
These are software that helps track changes made to files over time. It allows you to create different versions of files, revert to previous versions if needed, and collaborate effectively with others on projects. 
Its keeps track of every modification to the files in a special kind of a database where one can look at the project history and see:
<ol type='i'>
	<li> who has made the changes </li>
	<li> when the changes were made </li>
	<li> why the changes were made </li>
	<li> can also revert back to an initial state of the code </li>
</ol>
As a developer edits code, the version control system takes a snapshot of the files. It then saves that snapshot permanently so it can be recalled later if needed.
Without version control system, developers are tempted to keep multiple copies of their code on their computer. This is dangerous because it's easy to change or delete a file with the wrong copy/version of code, potentially losing work. This also makes the entire process very slow and not scalable especially if multiple people have to work on the same project.
As a result, developers will have to toss around the latest code via email or other mechanisms and then merge the changes. Version control solves this problem by managing all versions of the code but presenting the team with a single version at a time.

## Key concepts
Essential to understanding how version control systems actually work.
### 1. Repository (repo)
This is where all the project files and history of changes are stored. It acts a special type of database for the project files and its version history.
**Types**
1. **Local Repository** - Stored on your computer
2. **Remote Repository** - Stored on a server (e.g., GitHub, GitLab, BitBucket) 
### 2. **Commit**
Refers to a snapshot of your project at a specific point in time. Each commit represents a recorded change to your project, with a message describing what was done.
**Commit Message**: A description of the changes made, which should be clear and concise.