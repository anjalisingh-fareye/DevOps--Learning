# Day 11 – Git Reset, Revert & GitHub CLI

## Objective

The objective of this task is to understand how to undo changes in Git using `git reset` and `git revert`, and how to manage GitHub repositories using GitHub CLI.

---

# 1. Prerequisites

Before starting, make sure the following are installed:

- Git
- GitHub CLI
- GitHub account

Check Git:

```bash
git --version

Check GitHub CLI:

gh --version
2. Git Configuration

Configure Git username:

git config --global user.name "Anjali Singh"

Configure Git email:

git config --global user.email "your-email@example.com"

Check configuration:

git config --list
3. Create a Git Repository

Create a project directory:

mkdir git-reset-revert
cd git-reset-revert

Initialize Git:

git init

Check repository status:

git status
4. Create Files and Make Commits

Create a README file:

touch README.md

Add the file:

git add README.md

Create the first commit:

git commit -m "Initial commit"

Make another change:

echo "# Git Reset and Revert" >> README.md

Add and commit:

git add .
git commit -m "Add Git reset and revert documentation"

Check commit history:

git log --oneline
5. Understanding HEAD

HEAD represents the current location of the Git branch.

Check the current commit:

git log --oneline

Example:

a1b2c3d Add documentation
b2c3d4e Initial commit

HEAD points to the latest commit of the current branch.

HEAD
 ↓
a1b2c3d
 ↓
b2c3d4e
6. Git Reset

git reset is used to move the current branch to another commit.

There are three main types:

--soft
--mixed
--hard
6.1 Git Reset --soft
git reset --soft HEAD~1

It removes the latest commit but keeps the changes in the staging area.

Commit
  ↓
reset --soft
  ↓
Staging Area

Check:

git status
6.2 Git Reset --mixed
git reset --mixed HEAD~1

It removes the latest commit and unstages the changes, but keeps the changes in the working directory.

Commit
  ↓
reset --mixed
  ↓
Working Directory

--mixed is the default reset mode.

You can also use:

git reset HEAD~1
6.3 Git Reset --hard
git reset --hard HEAD~1

It removes the commit and resets the working directory and staging area to the selected commit.

Commit
  ↓
reset --hard
  ↓
Previous state
Warning

git reset --hard can permanently remove uncommitted work.

Always check:

git status

before using it.

7. Git Reset Comparison
Command	Commit	Staging Area	Working Directory
git reset --soft HEAD~1	Removed	Changes kept	Changes kept
git reset --mixed HEAD~1	Removed	Changes unstaged	Changes kept
git reset --hard HEAD~1	Removed	Changes removed	Changes removed
Easy way to remember
--soft  → Commit removed, changes staged
--mixed → Commit removed, changes unstaged
--hard  → Commit and local changes removed
8. Git Revert

git revert is used to undo the changes introduced by a previous commit.

Unlike git reset, revert creates a new commit.

Check history:

git log --oneline

Example:

a1b2c3d Add database
b2c3d4e Add login
c3d4e5f Initial commit

Revert a commit:

git revert a1b2c3d

Git creates a new commit that reverses the changes.

Initial commit
      ↓
Add login
      ↓
Add database
      ↓
Revert Add database
9. Reset vs Revert
Git Reset	Git Revert
Moves branch history	Creates a new commit
Can rewrite history	Preserves history
Useful for local work	Safer for shared branches
Can remove commits	Does not remove the original commit
git reset	git revert
Important

For a commit that has already been pushed to a shared branch such as main, git revert is generally safer.

Example:

git revert <commit-id>
git push
10. GitHub CLI

GitHub CLI is a command-line tool used to interact with GitHub from the terminal.

Command:

gh

Basic flow:

Terminal
   ↓
GitHub CLI
   ↓
GitHub
11. Check GitHub CLI
gh --version
12. GitHub CLI Authentication

Login:

gh auth login

Check authentication:

gh auth status
13. Create GitHub Repository Using CLI

Create a repository:

gh repo create

Create a public repository:

gh repo create git-reset-revert --public

Create a private repository:

gh repo create git-reset-revert --private
14. Connect Local Repository to GitHub

Check remote:

git remote -v

Add remote:

git remote add origin <repository-url>

Check again:

git remote -v
15. Push Code to GitHub

Rename branch to main:

git branch -M main

Push:

git push -u origin main

After upstream is configured:

git push
16. Clone a GitHub Repository

Using Git:

git clone <repository-url>

Using GitHub CLI:

gh repo clone OWNER/REPOSITORY
17. View Repository
gh repo view

Open repository in browser:

gh repo view --web
18. Pull Requests Using GitHub CLI

List Pull Requests:

gh pr list

Create Pull Request:

gh pr create

View Pull Request:

gh pr view

Open Pull Request in browser:

gh pr view --web

Merge Pull Request:

gh pr merge
19. GitHub Issues Using CLI

List issues:

gh issue list

Create an issue:

gh issue create

View an issue:

gh issue view <issue-number>
20. GitHub CLI Workflow
Create Branch
      ↓
Make Changes
      ↓
git add .
      ↓
git commit
      ↓
git push
      ↓
gh pr create
      ↓
Code Review
      ↓
gh pr merge
21. Complete Git Workflow
Working Directory
       ↓
   git status
       ↓
    git add
       ↓
   git commit
       ↓
 Local Repository
       ↓
    git push
       ↓
 GitHub Repository
       ↓
 Pull Request
       ↓
 Code Review
       ↓
 Merge


22. Practical Hands-on
Step 1 – Create Repository
mkdir git-practice
cd git-practice
git init
Step 2 – Create File
touch README.md
Step 3 – First Commit
git add .
git commit -m "Initial commit"
Step 4 – Make Changes
echo "Git Reset and Revert" >> README.md
Step 5 – Commit Changes
git add .
git commit -m "Add Git reset and revert"
Step 6 – Check History
git log --oneline
Step 7 – Practice Reset
git reset --soft HEAD~1

Check:

git status

Commit again:

git commit -m "Update Git documentation"
Step 8 – Practice Revert
git log --oneline

Then:

git revert <commit-id>

Check:

git log --oneline
Step 9 – Check GitHub CLI
gh auth status
Step 10 – Check Repository
gh repo view
Step 11 – Check Pull Requests
gh pr list
Step 12 – Check Issues
gh issue list
23. Important Commands
Git Reset
git reset --soft HEAD~1
git reset --mixed HEAD~1
git reset --hard HEAD~1
Git Revert
git revert <commit-id>
GitHub CLI
gh --version
gh auth login
gh auth status
gh repo create
gh repo clone OWNER/REPOSITORY
gh repo view
gh pr list
gh pr create
gh pr view
gh pr merge
gh issue list
gh issue create
gh issue view
24. Key Learnings
Understood Git reset.
Learned the difference between soft, mixed, and hard reset.
Understood Git revert.
Learned the difference between reset and revert.
Understood HEAD and commit history.
Learned GitHub CLI installation/version checking.
Learned GitHub CLI authentication.
Learned repository management using gh.
Learned Pull Request management using gh.
Learned GitHub Issue management using gh.
Practiced Git reset and revert hands-on.
