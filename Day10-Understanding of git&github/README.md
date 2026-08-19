#**Day 10 – Understanding Git and GitHub**#
1. Git

Day 10 – Understanding Git and GitHub
Objective

Understand the basics of Git and GitHub, create a Git repository, track changes, commit files, and push the repository to GitHub.

Topics Covered
1. Git

Git is a distributed version control system used to track changes in source code and files.

Git helps developers:

Track changes
Maintain code history
Create branches
Merge changes
Work with multiple developers
2. GitHub

GitHub is an online platform for hosting Git repositories. It is used for collaboration, code sharing, pull requests, issues, and project management.

3. Git vs GitHub
Git	GitHub
Version Control System	Online platform
Works locally	Works online
Tracks file changes	Hosts Git repositories
Uses commits and branches	Supports collaboration and code review
4. Creating a Git Repository

Create a project directory:

mkdir my-project
cd my-project

Initialize Git:

git init

git init creates a new Git repository in the current directory.

5. Git Configuration

Configure username:

git config --global user.name "Your Name"

Configure email:

git config --global user.email "your@email.com"

Check configuration:

git config --list
6. Basic Git Workflow
Working Directory
       ↓
    git add
       ↓
 Staging Area
       ↓
  git commit
       ↓
Local Repository
       ↓
   git push
       ↓
    GitHub
7. Important Git Commands
git status
git add .
git commit -m "commit message"
git log
git branch
git switch <branch>
git pull
git push
git clone <repository-url>
Examples

Check repository status:

git status

Add files:

git add .

Commit changes:

git commit -m "Initial commit"

View commit history:

git log
8. Create a README File
echo "# My Project" > README.md

Check the file:

cat README.md

Add and commit it:

git add README.md
git commit -m "Add README file"
9. Connect Local Repository to GitHub

After creating a repository on GitHub:

git remote add origin <github-repository-url>

Set the main branch:

git branch -M main

Push the code to GitHub:

git push -u origin main

Check the remote repository:

git remote -v
10. Practical Work Completed
Understood Git and GitHub
Installed and configured Git
Created a local Git repository
Created a README file
Checked repository status
Added files to the staging area
Created commits
Created a GitHub repository
Connected the local repository to GitHub
Pushed code to GitHub
Learned basic Git commands
Key Learning

Git is used for version control, while GitHub is used to host and collaborate on Git repositories.

Git Workflow
Code → git add → git commit → git push → GitHub

Create/Modify Code
       ↓
   git status
       ↓
    git add
       ↓
   git commit
       ↓
    git push
       ↓
     GitHub
Important Commands
git status
git add .
git commit -m "message"
git push
git pull
git clone <repo-url>
git branch
git switch <branch>
git merge <branch>
git log
Short Summary
Git → Version control
GitHub → Online Git repository
Repository → Project + Git history
Commit → Changes ka snapshot
Branch → Separate development line
Push → Local changes → GitHub
Pull → GitHub changes → Local machine

Git Repo ready karne ka basic process:

mkdir project
cd project
git init
git add .
git commit -m "Initial commit"
git remote add origin <github-repo-url>
git branch -M main
git push -u origin main
