# Git command
---
##### ***How to installing Git?***
1. Access the [git](https://git-scm.com/download/win) site
2. Download the git by choosing the right one out of 32 bits and 64 bits.
3. After installation, search for Gitbash in the Windows search box and run it.

---
### Changes vs. Snapshots
Storing Data as Changes
- Save storage space. Only changes are saved, reducing redundant data.
- It's easy to track the history of changes.
- It is easy to compare between different versions.
- You can combine the saved changes to get the latest snapshot.

Storing Data as Snapshots
- Each snapshot is a complete data snapshot, so there is less risk of data loss.
- Comparisons between snapshots can be costly.
- You can use a lot of storage space, especially if you have a large amount of data.

---

### Local, Centralized, and Distributed Version Control
1. Local Version Control
--Local version management is a method of performing version management on a single computer. It is primarily used when a single user manages a development project. The simplest form of local version management involves simply copying changes or creating backup files within folders. This approach has the following features:
- It only works on local systems and requires no network connection.
- Simple and fast to use.
- Not suitable for collaboration with other users.

2. Centralized Version Control
--  Centralized version management is the way central servers play a central role in a project. Multiple users can collaborate by importing and committing files from a central server. A case in point is Subversion (SVN). This approach has the following features:
- The central server contains the "truth" of the project and all changes are reflected on the central server.
- Collaboration between users is possible, but it is increasingly dependent on central servers, and failure of central servers can disrupt collaboration.

3. Distributed Version Control
-- Distributed version management is the way each user imports a copy of the entire store locally and works with it. The main examples are Git and Mercury. This approach has the following features:
- Each local copy has a full history, allowing you to work without network connectivity.
- Collaboration between users does not depend on central servers, enabling free and distributed development.
- Even if the central server fails, each user can continue working through a local copy

---

### Three States
1. Working Directory
-- A working directory is a directory that actually edits files and performs tasks. You can create, edit, and view the changes here.
2. Staging Area
-- The staging area is the space where changes are temporarily stored. You can optionally add or "stage" which of the files you changed in the working directory to commit to. Staging can be thought of as the last step to check before saving and committing changes.
3. Repository
-- Storage is a database of Git and stores a complete history of changes. When you commit changes to a staging area, the commit is stored in the repository. These repositories can be divided into local and remote repositories to track the history of projects and support collaboration.

---

### Git config: First-time setup
1. System Level
- System-level settings apply across your computer and affect all users and all repositories. These settings are configured by the system administrator or operating system settings that install Git.
- System-level settings are saved in the "/etc/gitconfig" file.
- System-level settings have lower priority than all other settings.
2. Global (User) Level
- Global level settings are relevant to the current user and apply to all of his repositories. This means that the same settings apply to all Git projects of one user.
- Global level settings are saved in the ~/.gitconfig file or the ~/.config/git/config file.
- Global level settings have a higher priority than system level settings.
3. Local Level 
- A local level setting is a setting for a specific Git store and applies only to that store. This setting provides custom configurations on a project-by-project basis.
- Local level settings are stored in the .git/gitconfig file in the repository.
- Local level settings overwrite system and global settings. In other words, per-store settings have the highest priority.
![](https://i.ibb.co/Nr8gb0K/1012-1.png)
---

### Initializing a Repository in an Existing Directory
- $git init
-- To initialize the Git store to a directory that already exists, use the gitinit command. This command creates a new Git repository within that directory.
1. Open the terminal and go to the directory:
Navigate to the directory where you want to initialize the Git repository. This directory may already exist and be the root directory of the project you want to manage with Git.
For example, to navigate to the project directory, use the command:
```
$cd /path/to/your/project
```
2. Run the 'git init' command:
Move to the desired directory and use the command below to initialize the Git repository:
```
$git init
```
This command creates the .git directory in a hidden form within the directory. This directory stores all settings, commit history, and other information about the Git repository.
3. Configure Git Storage:
Initializing the Git repository creates a Git setup file that is stored in the .git directory. You can use these settings files to change user information, branch settings, and other configurations.

---

### Checking Repository Status
- $git status
-- The 'git status' command is used to determine the status of the current working directory within the Git repository. This command displays changes that have not yet been staged, changes that have not been committed, current branches, and other useful information. The 'git status' command is one of the important tools to use Git, which helps you understand the current state of the project and perform version management more effectively.
![](https://i.ibb.co/ZLR1nJY/1012-3.png)

---

### Adding a new file to be staged(tracked)
- $git add[file_name]
--The command 'git add [file_name]' is used by Git to add new files to the staging area. This command allows Git to track and prepare to commit to that file.
![](https://i.ibb.co/jZKQ9Y7/1012-2.png)
![](https://i.ibb.co/zSQrtmy/1012-4.png)
![](https://i.ibb.co/2PN1gLg/1012-5.png)
![](https://i.ibb.co/jDC6r1L/1012-6.png)

- $git add.
--The 'git add' command is used by Git to add files or changes to the staging area. Files in the staging area are included in the following commitments. The 'gitadd' command can be used in many ways.
![](https://i.ibb.co/qFq5dfD/1012-7.png)

---

### Unstaging a file
- git rm --cached [file_name]
--You can use the command 'gitrm --cached [file_name]' to unstage files in the staging area. This command removes the file from the staging area, but it remains in the working directory. This is useful if you accidentally staged a file, or if you want to remove the file from staging before staging the file you tried to stage again.
![](https://i.ibb.co/xD6kTvC/1012-8.png)

---

### Ignoring a file
- To ignore files in Git.Use 'gitignore' file. The file '.gitignore' is responsible for instructing Git to ignore a particular file or directory. This file is usually created in the Git store root directory and is named '.gitignore'.
-- To set which files or directories to ignore using the file '.gitignore':
1. Create a .gitignore file:
First, create a .gitignore file from the root directory of the Git repository.
2. Use pattern to ignore files:
.Open the gitignore file and specify the pattern of the file or directory you want to ignore. Patterns represent paths or extensions.
3. Add files to .gitignore:
.Add the file you want to ignore to the gitignore file and save it.
4. Commit the .gitignore file to Git:
.Commit the gitignore file to the git store to save the settings.
![](https://i.ibb.co/z2Tpq8z/1012-9.png)

- .gitignore file
![](https://i.ibb.co/Sy3tBHF/1012-10.png)

---

### Commit
- $ git commit-m "commit message"
-- The git commit -m "commit message" command is used to create a new commit in Git and provide a description of this commit, including a commit message. Commit messages play an important role in managing Git history and changes.Below is a description of how to use the git commit command:
1. Staging changes:
Changes must be added to the staging area first. Use the git add command to add changes to the staging area.
2. Create commit message:
When creating a commit, use the git commit -m command to create a commit message. The commit message must be a concise description of the commit and contain information related to the changes. Commit messages should be written in an easy way to understand what changes have been made, from small to large changes.
3. Create commit:
Run the git commit -m "commit message" command to generate a commit. Commit messages must be written in double quotes.
4. Confirm commit:
To verify the commit, use the git log command to verify the history. Use this command to view previous commitments and commit messages.
![](https://i.ibb.co/fkZszTt/1012-11.png)

---

### Change branch name
--Here's how to rename a branch in Git:
![](https://i.ibb.co/YZ3pJSR/1012-12.png)
