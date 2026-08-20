# **Day 12 – Advanced Git**

## **Objective**

Understand advanced Git concepts and revise all previously learned Git and GitHub concepts.

---

## **Topics Covered**

- **Git Merge**
- **Fast-Forward Merge**
- **Three-Way Merge**
- **Merge Conflict**
- **Git Rebase**
- **Interactive Rebase**
- **Git Stash**
- **Git Cherry-Pick**
- **Git Reset**
- **Git Revert**
- **Git Branch**
- **Git Push / Pull**
- **GitHub CLI**
- **Pull Request**
- **Revision of Git Concepts**

---

## **1. Git Merge**

- **Merge** is used to combine changes from one branch into another.
- Learned **Fast-Forward Merge**.
- Learned **Three-Way Merge**.
- Practiced merging feature branches into `main`.

```bash
git switch main
git merge feature

git status
git add .
git commit
git merge --abort
git switch feature
git rebase main

2. Merge Conflict
Merge Conflict occurs when Git cannot automatically combine changes.
Learned how to identify conflicts.
Resolved conflicts manually.
Learned how to abort a merge.
git status
git add .
git commit
git merge --abort
3. Git Rebase
Rebase is used to apply commits on top of another base branch.
Learned how rebase creates a cleaner linear history.
Practiced rebasing a feature branch onto main.
git switch feature
git rebase main
4. Interactive Rebase
Interactive Rebase is used to modify commit history.
Learned:
pick
reword
edit
squash
fixup
drop
git rebase -i HEAD~3
5. Merge vs Rebase
Merge	Rebase
Combines branches	Replays commits
May create merge commit	Creates linear history
Preserves history	Rewrites commit history
Safer for shared branches	Better for local/private branches
6. Git Stash
Git Stash temporarily saves uncommitted changes.
Useful when we need to switch branches without committing incomplete work.
Commands
git stash
git stash list
git stash apply
git stash pop
git stash drop
git stash clear
Workflow
Working Changes
      ↓
  git stash
      ↓
Clean Working Directory
      ↓
Switch Branch
      ↓
git stash pop
7. Git Cherry-Pick
Cherry-Pick is used to apply a specific commit from another branch.
Useful when we need only one particular commit.
git cherry-pick <commit-id>
Conflict Handling
git status
git add .
git cherry-pick --continue

Abort:

git cherry-pick --abort
8. Merge vs Rebase vs Cherry-Pick
Operation	Purpose
Merge	Combine branches
Rebase	Reapply commits on another base
Cherry-Pick	Apply a specific commit
9. Git Reset
Reset is used to move the current branch to another commit.
Learned Soft Reset.
Learned Mixed Reset.
Learned Hard Reset.
git reset --soft HEAD~1
git reset --mixed HEAD~1
git reset --hard HEAD~1
Reset Types
Reset	Result
Soft	Commit removed, changes remain staged
Mixed	Commit removed, changes remain unstaged
Hard	Commit and local changes removed
10. Git Revert
Revert is used to undo an existing commit.
It creates a new commit.
It preserves the existing commit history.
Generally safer for shared branches.
git revert <commit-id>
11. GitHub CLI
GitHub CLI (gh) allows us to manage GitHub directly from the terminal.
Authentication
gh auth login
gh auth status
Repository
gh repo create
gh repo view
gh repo clone OWNER/REPOSITORY
Pull Request
gh pr list
gh pr create
gh pr view
gh pr merge
Issues
gh issue list
gh issue create
12. Complete Git Workflow
Create Repository
       ↓
Create Branch
       ↓
Make Changes
       ↓
git add
       ↓
git commit
       ↓
git push
       ↓
Pull Request
       ↓
Code Review
       ↓
Merge / Rebase
       ↓
CI/CD Pipeline
       ↓
Deploy
13. Revision of All Git Concepts
Git
GitHub
Git Repository
Working Directory
Staging Area
Commit
HEAD
Branch
Merge
Merge Conflict
Rebase
Interactive Rebase
Stash
Cherry-Pick
Reset
Revert
Remote Repository
Push
Pull
Clone
Pull Request
GitHub CLI
14. Practical Hands-on
Merge Practice
git switch main
git merge feature
Rebase Practice
git switch feature
git rebase main
Stash Practice
git stash
git stash list
git stash pop
Cherry-Pick Practice
git log --oneline
git cherry-pick <commit-id>
Reset Practice
git reset --soft HEAD~1
Revert Practice
git revert <commit-id>
15. Important Commands
# **Merge**
git merge <branch>


# **Rebase**
git rebase <branch>
git rebase -i HEAD~3


# **Stash**
git stash
git stash list
git stash apply
git stash pop
git stash drop


# **Cherry-Pick**
git cherry-pick <commit-id>


# **Reset**
git reset --soft HEAD~1
git reset --mixed HEAD~1
git reset --hard HEAD~1


# **Revert**
git revert <commit-id>


# **GitHub CLI**
gh auth status
gh repo create
gh repo view
gh pr list
gh pr create
gh pr merge
gh issue list
16. Key Learnings
Understood Git Merge and Merge Conflicts
Learned Git Rebase and Interactive Rebase
Learned Git Stash for temporary changes
Learned Git Cherry-Pick
Understood Reset vs Revert
Learned GitHub CLI
Revised Git Branching and GitHub Workflow
Practiced Advanced Git Commands
17. DevOps Perspective
Developer
    ↓
Git
    ↓
GitHub
    ↓
Pull Request
    ↓
Code Review
    ↓
CI/CD
    ↓
Build
    ↓
Test
    ↓
Deploy
    ↓
Monitoring
Conclusion

Advanced Git concepts such as Merge, Rebase, Stash and Cherry-Pick help developers manage branches, commits, conflicts and collaboration efficiently in real-world DevOps environments.
