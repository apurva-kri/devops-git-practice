## Day 22 – Introduction to Git: My First Repository
# Task 1: Install and Configure Git
<img width="583" height="376" alt="git1" src="https://github.com/user-attachments/assets/41913ef5-9d8b-4f55-acf1-472072ecb2a6" />

# Task 2: Create Your Git Project
<img width="832" height="265" alt="Screenshot 2026-03-11 052925" src="https://github.com/user-attachments/assets/e4bf8ed8-38e2-4e76-85bd-0246226224ce" />

<img width="706" height="58" alt="Screenshot 2026-03-11 061430" src="https://github.com/user-attachments/assets/90d0e1a5-c2bf-4842-8df7-0197ad208009" />

# Task 3: Create Your Git Commands Reference
## Git Commands Reference
# Setup & Config

- git --version , Shows the installed Git version.
```
git --version
```
- Sets your global Git username , git config --global user.name
```
git config --global user.name "Rahul Sharma"
```
- git config --global user.email
- Sets your global Git email address.
```
git config --global user.email "rahul@gmail.com"
```
- git config --list
- Displays all Git configuration settings.
```
git config --list
```
# Basic Workflow
- git init , Initializes a new Git repository.
```
git init
```
# mkdir , Creates a new directory.
```
mkdir devops-git-practice
```
# cd , Changes the current directory.
```
cd devops-git-practice
```
# touch , Creates a new file.
```
touch git-commands.md
```
# Viewing Changes - git status
- Shows the current status of the repository including tracked and untracked files.
```
git status
```
# Task 4: Stage and Commit- Staging & Committing

# git add - Adds files to the staging area.
```
git add git-commands.md
```
# git commit -m , Saves staged changes with a message.
```
git commit -m "Add git commands reference documentation"
```
![commit](image.png)
# git log - Displays commit history.
```
git log
```
# git log --oneline - Shows a compact version of commit history.
```
git log --oneline
```
![git oneline](image-1.png)

# Visual Git Workflow (Very Important)
```
Working Directory
        │
        │ git add
        ▼
Staging Area
        │
        │ git commit
        ▼
Git Repository (History)
```
## Task 5- Make More Changes and Build History
## Branching
# git branch - Shows all branches in the repository.
```
git branch
```
# git checkout - Switches to another branch.
```
git checkout main
```
# Task 6: Understand the Git Workflow
- Step 1: Create the Notes File
```
touch day-22-notes.md
```
- What is the difference between git add and git commit?
- Ans: git add moves changes from the working directory to the staging area. It prepares the files that will be included in the next commit. Git commit saves the staged changes into the Git repository as a permanent snapshot with a message explaining what changed.
- Example workflow:
```
git add file.txt
git commit -m "Added new feature"
```
- What does the staging area do? Why doesn't Git just commit directly?
- Ans: The staging area is a place where you prepare changes before committing them. It allows you to select exactly which changes should go into the next commit. Git uses a staging area so developers can group related changes together instead of committing everything at once.

- What information does git log show you?
- Ans: git log shows the commit history of the repository.
It includes:
- Commit ID (unique hash)
- Author name and email
- Date of the commit
- Commit message

- What is the .git/ folder and what happens if you delete it?
- Ans: The .git folder is the hidden directory that stores all Git data for the repository. It contains commits, branches, configuration, and history. If the .git folder is deleted, the project is no longer a Git repository and all version history is lost.

- What is the difference between a working directory, staging area, and repository?
- Working Directory  
This is the folder where you edit and create files on your computer.

Staging Area  
This is where files are prepared before committing. Files are added here using git add.

Repository  
This is where Git permanently stores committed versions of files along with the project history.
- List all branches in your repo
```
git branch
```
- Create a New Branch Called feature-1
```
git branch feature-1
```
- Switch to feature-1
```
git checkout feature-1
```
## Create a new branch and switch to it in a single command — call it feature-2
```
- git checkout -b feature-2
```
## Try using git switch to move between branches — how is it different from git checkout?
```
git switch feature -1
```
## Difference Between checkout and switch
- git checkout - Older command used for switching branches AND restoring files
- git switch - Newer command used only for switching branches, simpler and safer

## Make a Commit on feature-1 (Not on Main)
- git switch feature-1
- ### git branch
Lists all branches in the repository.
Example:
git branch

- git add git-commands.md
- git commit -m "Add branching commands documentation"
- Switch Back to main and Verify - The commit from feature-1 is NOT in main.
![git switch](image-3.png)
![git main](image.png)

- Delete a Branch You No Longer Need
```
git branch -D feature-2
```
## Task 3: Push to GitHub
- What is origin? - origin is the default name for the main remote repository that your local repo is connected to. When you clone a repository, Git automatically creates origin.
-Example:
```
git clone https://github.com/user/project.git
git remote -v
you will see:
origin  https://github.com/user/project.git (fetch)
origin  https://github.com/user/project.git (push)
```
- So origin usually means:Your GitHub repository where you push your code, eg: git push origin main

- What is upstream? - upstream is usually used when you fork someone else's repository.
In this case:

origin → your forked repository
upstream → the original repository you forked from
```
- Example structure:
Original repo (someone else's project)
        ↑
     upstream
        ↑
Your fork on GitHub
        ↑
      origin
        ↑
   Your local machine
   ```
  - What is the difference between git fetch and git pull?
  - git fetch downloads the latest changes from the remote repository but does NOT modify your local working files. It only updates the remote tracking branches. Fetch means download updates only.
  - git pull downloads changes AND immediately merges them into your current branch.

## Task 5: Clone vs Fork
- What is the difference between clone and fork?
Clone creates a copy of a repository from GitHub (or another remote) to your local machine.
You use it when you want to download a repository and start working on it locally.
```
GitHub Repository
        │
        │ git clone
        ▼
Your Local Machine
```
Clone = copy repo from remote → local machine

- A fork creates a copy of someone else's repository in your own GitHub account.
You usually fork a project when you do not have write access to the original repository but want to contribute.
Forking is done on GitHub's website, not through a Git command.

- When would you clone vs fork?
Use clone when you want to work directly on a repository you have access to.
- This is common in:
Your own repositories
Team/company projects
Internal projects where you already have write permission
```
GitHub Repo
      │
      │ git clone
      ▼
Local Machine
      │
      │ commit + push
      ▼
Same Repository
```
- Use fork when you want to contribute to a repository but you do NOT have write access.

This is common in:
Open-source projects
External repositories
Projects owned by other organizations
-You cannot push directly.
So you:
1️⃣ Fork the repository
2️⃣ Clone your fork
3️⃣ Push changes to your fork
4️⃣ Create a Pull Request
```
Original Repo
      │
      │ fork
      ▼
Your GitHub Repo
      │
      │ clone
      ▼
Local Machine
      │
      │ push
      ▼
Your Fork
      │
      │ Pull Request
      ▼
Original Repo
```
- After forking, how do you keep your fork in sync with the original repo?
To keep your fork updated with the original repository, you need to connect the original repo as upstream and pull changes from it. 
## Step 1: Clone Your Fork
- First, clone your fork from GitHub:
``` git clone https://github.com/YOUR-USERNAME/repository-name.git ```
- Step 2: Add the Original Repository as upstream
``` git remote add upstream https://github.com/ORIGINAL-OWNER/repository-name.git ```
-check remotes:
``` git remote -v ```
Example o/p- 
``` 
origin   https://github.com/YOUR-USERNAME/repository-name.git
upstream https://github.com/ORIGINAL-OWNER/repository-name.git
```
- Step 3: Fetch Changes from the Original Repo - Download updates from the original repo:
```git fetch upstream``` This downloads changes but does not merge them yet.
-Step 4: Update Your Local Branch - Switch to the main branch:
``` git switch main ``
Merge updates from upstream:
``` git merge upstream/main ``` Now your local repo has the latest changes.
- Step 5: Push Updates to Your Fork - Update your fork on GitHub:
``` git push origin main```
- Full Sync Workflow
```
git fetch upstream
git switch main
git merge upstream/main
git push origin main
```
```
Original Repo (upstream)
        │
        │ fetch
        ▼
Local Repository
        │
        │ push
        ▼
Your Fork (origin)
```
# Git Reset — Hands-On
- git reset --soft
- git reset --mixed