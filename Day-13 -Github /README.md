# Day 13: Understanding GitHub Actions

GitHub Actions is a Continuous Integration and Continuous Deployment (CI/CD) platform integrated directly into GitHub. It allows you to automate your build, test, and deployment pipeline using YAML workflows.

---

## 🚀 Key Concepts

- **Workflow**: An automated process defined in a `.yml` file inside `.github/workflows/`.
- **Event**: A specific activity that triggers a workflow (e.g., `push`, `pull_request`, `schedule`).
- **Job**: A set of steps executed on the same runner environment.
- **Step**: An individual task inside a job (runs a terminal command or calls a reusable action).
- **Runner**: A virtual server hosted by GitHub (or self-hosted) running Ubuntu, Windows, or macOS.

---

## 📊 Core Components Overview

| Component | YAML Key | Purpose |
| :--- | :--- | :--- |
| **Name** | `name:` | Identifies the workflow in the GitHub Actions tab |
| **Triggers** | `on:` | Specifies events that fire the workflow |
| **Runner** | `runs-on:` | Defines the virtual OS environment |
| **Jobs** | `jobs:` | Groups one or more execution tasks |
| **Steps** | `steps:` | Array of commands (`run`) or actions (`uses`) |

---

## ⚙️ Practical Workflow Example

Place this file in `.github/workflows/ci.yml` within your project root:

```yaml
name: Node.js CI Pipeline

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

jobs:
  build-and-test:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout Source Code
        uses: actions/checkout@v4

      - name: Set up Node.js Environment
        uses: actions/setup-node@v4
        with:
          node-version: '20'

      - name: Install Dependencies
        run: npm ci

      - name: Run Test Suite
        run: npm test

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
