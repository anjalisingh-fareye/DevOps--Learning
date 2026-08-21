# Git Reset, Revert & GitHub CLI

## Objective

Understand **Git Reset**, **Git Revert**, and **GitHub CLI** with practical commands.

## Topics Covered

- **Git Reset**
- **Git Revert**
- **Reset Modes**
- **Reset vs Revert**
- **GitHub CLI**
- **Repository Creation**
- **Pull Request Management**

## Git Reset vs Git Revert Concepts

### Git Reset

Used to move the current branch to an earlier commit and can modify local history.

### Git Revert

Creates a new commit that reverses the changes of an existing commit, making it suitable for shared history.

## Git Reset Modes

### Soft Reset

```bash
git reset --soft HEAD~1

Mixed Reset
git reset --mixed HEAD~1

Keeps the changes in the Working Directory.

Hard Reset
git reset --hard HEAD~1

Resets the working tree and staging area to the target commit. Use carefully because uncommitted changes can be lost.

Git Revert
git revert <commit-hash>

Creates a new commit that reverses the selected commit.

Reset vs Revert
Feature	Git Reset	Git Revert
History	Rewrites local history	Preserves history
Best Used For	Local/unfinished history	Shared/pushed commits
Safety	Use carefully	Safer for shared branches
GitHub CLI

GitHub CLI (gh) allows GitHub operations directly from the terminal.

Authentication
gh auth login
gh auth status
Repository
gh repo create
gh repo view
gh repo clone OWNER/REPOSITORY
Pull Request
gh pr create
gh pr list
gh pr view
gh pr merge
Practical
Create Repository
gh repo create git-reset-revert-github-cli --public
Check Repository
gh repo view
Check Authentication
gh auth status
Key Learnings
Understood Git Reset
Learned Soft, Mixed and Hard Reset
Understood Git Revert
Learned Reset vs Revert
Learned GitHub CLI
Created and managed a GitHub repository from the terminal
Learned basic Pull Request commands


### **`commands/git-commands.md`**


Isme sirf commands rakho:


```markdown
# Git & GitHub CLI Commands


## Git Reset


```bash
git reset --soft HEAD~1
git reset --mixed HEAD~1
git reset --hard HEAD~1
Git Revert
git revert <commit-hash>
GitHub CLI
gh --version
gh auth login
gh auth status
gh repo create
gh repo view
gh repo clone OWNER/REPOSITORY
gh pr create
gh pr list
gh pr view
gh pr merge


### **Final repo structure**


```text
📁 git-reset-revert-github-cli
│
├── 📄 README.md
│
└── 📁 commands
    └── 📄 git-commands.md
