# Day 13 – Understanding GitHub Actions

 Objective

 1. Objective

Understand GitHub Actions and how it is used to automate CI/CD workflows.

2. What is GitHub Actions?

GitHub Actions is a CI/CD and automation platform provided by GitHub. It automatically performs tasks such as build, test, and deployment when an event occurs in a repository.

3. Main Components
Workflow – Defines the automation process.
Event – Defines when the workflow runs, such as push or pull_request.
Job – A group of tasks.
Step – An individual task inside a job.
Action – A reusable automation component.
Runner – The machine where the job runs.
4. Workflow File

Workflows are stored in:

.github/workflows/ci.yml

Example:

name: CI Pipeline


on:
  push:
    branches:
      - main


jobs:
  build:
    runs-on: ubuntu-latest


    steps:
      - name: Checkout Code
        uses: actions/checkout@v4


      - name: Build
        run: echo "Build successful"


      - name: Test
        run: echo "Test successful"
5. Important Topics
CI/CD
Workflow
Triggers
Jobs and Steps
Runners
Actions
Environment Variables
GitHub Secrets
Artifacts
Workflow Logs
6. Practical

Created a basic CI workflow and verified its execution from:

GitHub Repository → Actions

7. Key Learning

GitHub Actions automates software development workflows such as building, testing, and deploying applications directly from GitHub.

Repository Structure
github-actions-learning/
├── README.md
└── .github/
    └── workflows/
        └── ci.yml

 What is GitHub Actions?

 What is CI/CD?

 GitHub Actions Architecture

 Workflow

 Events / Triggers

 Jobs

Steps

 Actions

Runners

Workflow YAML File

`uses` vs `run`

Environment Variables

GitHub Secrets

 Artifacts

Workflow Logs

 Pull Request Workflow

 Practical Implementation

 Important Commands

 Key Learnings

DevOps Workflow

2. GitHub Actions Workflow

Create this structure:

.github/
└── workflows/
    └── ci.yml

Example ci.yml:

name: CI Pipeline


on:
  push:
    branches:
      - main


  pull_request:
    branches:
      - main


jobs:
  build:
    runs-on: ubuntu-latest


    steps:
      - name: Checkout Code
        uses: actions/checkout@v4


      - name: Check Files
        run: ls -la


      - name: Build
        run: echo "Build successful"


      - name: Test
        run: echo "Test successful"
3. Practical Proof

After pushing the workflow:

GitHub Repository → Actions

Check:

Workflow Run
Jobs
Steps
Success / Failure
Workflow Logs

You can also add a screenshot of the successful workflow run to your repository.

Final Repository Structure
github-actions-learning/
│
├── README.md
│
└── .github/
    └── workflows/
        └── ci.yml
Remember

README.md → What you learned
ci.yml → What you implemented
Actions Run → Proof that your workflow executed successfully.
